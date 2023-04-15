namespace :db do
  desc 'migrate changes to your database'
  task migrate: :environment do
    Student.create_table
  end
end

task :environment do
  require_relative './config/environment'
end

desc 'drop into the Pry console'
task :console => :environment do
  require 'pry'
  Pry.start
end

desc 'migrate changes to your database'
task 'db:migrate' => :environment do
  Student.create_table
end

desc "Print hello from Rake!"
task "greeting:hello" do
  puts "hello from Rake!"
end

desc "Print hola de Rake!"
task "greeting:hola" do
  puts "hola de Rake!"
end

desc "Migrate the database"
task "db:migrate" => :environment do
  # Implementation of db:migrate task
end

desc "Seed the database"
task "db:seed" => :environment do
  dummy_data = [
    { name: "Melissa", grade: "10th" },
    { name: "April", grade: "10th" },
    { name: "Luke", grade: "9th" },
    { name: "Devon", grade: "11th" },
    { name: "Sarah", grade: "10th" }
  ]

  dummy_data.each do |data|
    Student.create(name: data[:name], grade: data[:grade])
  end

  puts "Seeded the database with #{dummy_data.length} records."
end
