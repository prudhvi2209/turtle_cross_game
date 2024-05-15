#MAIN ............   

from turtle import Screen
from player import Player
import time
from car_manager import CarManager
from scoreboard import Scoreboard

screen=Screen()
screen.tracer(0)
screen.bgcolor("white")
screen.title("Welcome to Turtle Race!!!!")
player=Player()
car_manager=CarManager()
scoreboard=Scoreboard()



screen.listen()
screen.onkey(player.move, "Up")


game_on=True
while game_on:
    time.sleep(0.1)
    screen.update()
    car_manager.create_cars()
    car_manager.move_cars()

    for car in car_manager.all_cars:
        if car.distance(player)<20:
            game_on=False
            scoreboard.game_over()
    if player.is_at_finish_line():
        player.origin()
        car_manager.level_up()
        scoreboard.increase_level()




screen.exitonclick()

