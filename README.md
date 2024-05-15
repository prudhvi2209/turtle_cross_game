from turtle import Turtle
STARTING_POSITION=(0,-240)
FINISH_LINE=(0,240)
class Player(Turtle):

    def __init__(self):
        super().__init__()
        self.color("black")
        self.shape("turtle")
        self.penup()
        self.goto(STARTING_POSITION)
        self.setheading(90)

    def move(self):
        self.new_y=self.ycor()+20
        self.goto(self.xcor(),self.new_y)

    def origin(self):
        self.goto(STARTING_POSITION)

    def is_at_finish_line(self):
        if self.ycor()>240:
            return True
        else:
            return False
