
task :default => 'morning:turn_off_alarm'    

namespace :morning do
  desc "turn off alarm"
  task :turn_off_alarm do
    puts "Turned off alarm. Would have liked 5 more minutes, though."
  end

  desc "groom myself"
  task :groom_myself do
    puts "Brushed teeth."
    puts "Showered."
    puts "Shaved."
  end
  
  desc "make coffee on morning"
  task :make_coffee do
    cups = ENV["COFFEE_CUPS"] || 2
    puts "Made #{cups} cups of coffee. Shakes are gone."
  end
   
  desc "walk dog"
  task :walk_dog do
    puts "Dog walked."
  end
 
  desc "ready for the day -> calls other tasks"
  task :ready_for_the_day => [:turn_off_alarm, :groom_myself, :make_coffee, :walk_dog] do
    puts "Ready for the day!"
  end
end


namespace :afternoon do
  desc "make coffe on afternoon"
  task :make_coffee do
    Rake::Task['morning:make_coffee'].invoke
    puts "Ready for the rest of the day!"
  end
end