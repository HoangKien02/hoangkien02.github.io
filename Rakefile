desc 'Start development server'
task :dev do |task|
  system "bundle exec jekyll serve --livereload --force_polling --host 0.0.0.0 --port 4000"
end

namespace :posts do
  desc "Create a new post"
  task :new do |task|
    input = {}

    puts "Creating a new post. Please enter the information."
    print "Title: "
    input[:title] = STDIN.gets.strip
    if input[:title].length == 0
      puts "Title must be at least 1 character long."
      next
    end
    
    print "URL slug: "
    input[:slug] = STDIN.gets.strip
    if input[:slug].length == 0
      puts "URL slug must be at least 1 character long."
      next
    end

    puts "Create post with the following content? (Y/n)"
    puts input.inspect

    unless STDIN.gets.strip.downcase == 'y'
      puts "Cancelled."
      next
    end

    now = Time.now
    post_dir = "_posts/#{now.strftime("%Y")}"
    Dir.mkdir(post_dir) unless Dir.exists?(post_dir)
    filepath = "#{post_dir}/#{now.strftime("%Y-%m-%d")}-#{input[:slug]}.md"
    puts "Creating file: #{filepath}"
    File.open(filepath, 'w') do |f|
      f.write(<<"POST"
---
layout: post
title: #{input[:title]} 
date:  #{now.strftime("%Y-%m-%d %H:%M:00 %z")}
tags: []
---
new post 
POST
      )
    end
    puts "File created: #{filepath}"
  end
end
