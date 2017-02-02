# encoding: utf-8
#
# Copyright (c) 2016-2017 Zerocracy
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to read
# the Software only. Permissions is hereby NOT GRANTED to use, copy, modify,
# merge, publish, distribute, sublicense, and/or sell copies of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

require 'nokogiri'
require 'rake'
require 'rake/clean'
require 'date'
require 'fileutils'

task default: [:clean, :xsd, :copyright]

desc 'Validate all XML/XSD files'
task :xsd do
  total = 0
  Dir.mktmpdir do |temp|
    FileUtils.cp_r('xsd/', temp)
    Dir[temp + '/**/*.xsd'].each do |f|
      File.write(
        f,
        File.read(f).gsub(
          'http://raw.githubusercontent.com/zerocracy/datum/0.16/xsd',
          temp + '/xsd'
        )
      )
    end
    Dir['xml/**/*.xml'].each do |p|
      print "Checking #{p}... "
      f = p.sub(/xml\//, temp + '/xsd/').sub(/\/[^\/]+\.xml$/, '.xsd')
      begin
        xsd = Nokogiri::XML::Schema(File.open(f))
      rescue Nokogiri::XML::SyntaxError => e
        print "\n#{f} #{e.line}: #{e.message}"
        raise 'XSD is invalid'
      end
      ok = true
      xml = Nokogiri::XML(File.read(p))
      if File.basename(p).start_with?('-')
        if xsd.validate(xml).empty?
          print "#{p} no errors, but we are expecting some\n"
          total += 1
          ok = false
        end
      else
        xsd.validate(xml).each do |error|
          puts "\n#{p} #{error.line}: #{error.message}"
          total += 1
          ok = false
        end
      end
      print "OK\n" if ok
    end
  end
  raise "#{total} errors" unless total == 0
  puts 'All XML/XSD files are clean'
end

task :copyright do
  sh "grep -q -r '2016-#{Date.today.strftime('%Y')}' \
    --include '*.rb' \
    --include '*.xml' \
    --include '*.xsd' \
    --include '*.txt' \
    --include 'Rakefile' \
    ."
end
