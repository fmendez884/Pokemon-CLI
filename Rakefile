require_relative 'config/environment'
require_relative 'models/pokeball.rb'
require_relative 'models/pokemon.rb'
require_relative 'models/user.rb'
require_relative 'models/battle.rb'
require_relative 'lib/cli.rb'
require 'sinatra/activerecord/rake'
require 'tty-prompt'

desc 'starts a console'
task :console do
	user1 = User.all.first
	user2 = User.all.last 
	battle1 = Battle.new(user_id: user1.id, opponent_id: user2.id, user: user1, opponent: user2)
	# Pry.start
	battle1.battle_state
	binding.pry
end

desc 'runs CLI'
task :cli do
	cli = CommandLineInterface.new
	cli.main_menu
end

desc "Rewrites abridged _pokedex.json as ./db/seeds.json "
task :format_json do
	JsonFormatter.new
end

desc 'TTY-Prompt'

task :tty do
	require 'tty-prompt'
	prompt = TTY::Prompt.new
	Pry.start
end

desc 'Battle Tester'
task :damage_calc do 
	pokemon1 = Pokemon.first 
	pokemon2 = Pokemon.last 
	squirtle = Pokemon.find_by(name: "Squirtle")
	bulbasaur = Pokemon.find_by(name: "Bulbasaur")

	stat_difference = (pokemon1.attack / pokemon2.defense)
	rando = Battle.rando255

	binding.pry
end 
