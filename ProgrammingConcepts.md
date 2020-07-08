ProgrammingConcepts

<Shapes>
	rect 			: GameScreen
		   			  character(with moving x, moving y)
		   			  buttons

	round(ellipse)  : Obstacles(Blacl balls, Red balls)
					  googly eyes(angle += 0.05)

	text 			: score
					  How to Play
					  buttons
					  title
					  game over screen

<Colors>
	Background Color 	: Pink
	GameScreen Stroke	: Plum
	Character Color 	: Random
	Black ball Color 	: Black(0)
	Red ball Color 		: Red
	Game Over text 		: Red
	Game Over Stroke 	: White(255)
	Buttons 			: Gray(220)

<Variables>
	const MAIN_MENU = 1;
	const CREDITS_SCREEN = 2;
	const OPTIONS_SCREEN = 3;
	const GAME = 4;
	const GAME_OVER = 5;
						Scenes are used for change the page.

	let CurrentScene = MAIN_MENU;

	let MainScene;
	let CreditsScene;
	let OptionsScene;
	let GameScene;
	let GameoverScene;

	var HEART;
	var bgm = 1;		is used for music on/off
	var BGM;

	var balls1 = [];
	var balls2 = [];
						make obstacles.

	var chance = 3;		left life.
	var life;
	var showscore;
	var score = -1;
	var a = 1;			music on/off > bgm += a; if(bgm % 2 == 1){}
	var move = 0;		is used for player go/stop
	var playercolor = 150;		default color
	var stage = 0;

<Conditional Statements>
	switch(CurrentScene){
	case A:
}
		When you click the buttons, CurrentScene would be changed as button that you clicked.
	
	if(ball crash player){
		life -= 1;
	}
		When you crash with obstacles, you would lose your life(chance).
		Put the range of balls and player. When range of ball < range of player --> -1 life.

	if(blackballs > 50) {
		splice() --> remove the oldest one
	}
		If there are too many balls in screen, the ball which is the oldest would be removed automatically.

	if(life < 1) {
		noLoop;
		-->
			no more balls
			balls move stop
			character stop
			Gameover screen comes out
			Score would come out center of the screen
	}

	if(changed side which character is on) {
		side += 1 --> is used for character to move which one stopped.
		change the direction
		rotate the googly eyes
	}

	if(click the sound button at option){
		bgm += 1
	}
		It is used to play and stop the Background Music.

	if(bgm % 2 == 1){
		stop bgm
	}

	if(click the color button at option){
		playercolor = random
	}

<Loops>
	setInterval(balls function, second)
		The obstacles come out every each time.

	setInterval(score function, second)
		Make score bigger.

	for(balls count that comes out once){
		array push
	}
		Make new Obstacles.

	for(ball length) {
		balls[i].update()
		balls[i].attack()
	}
		Draw new Obstacles.

<Functions>
	preload()		: Load media files.
	GameScreen()	: Draw Game Screen.
	DrawTitle(label): Draw Titles at each page.
	Current()		: Make each scenes comes out when they called with switch(					  CurrentScene).
	keyPressed()	: if the key is space, move += 1 and it is related with 					  character's moving.
	Black()			: Make new black balls.
	Red()			: Make new red balls.
	Drawballs()		: Draw black and red balls and also remove the old balls.
						balls[i].update();
						balls[i].draw();
						balls.splice(0, 1);
	Chance()		: Show the left chance(heart/life).
						if(life >= 1){(draw heart)}
	getScore()		: Make score bigger number every its time.
	Game_Over()		: Show game over contents such as text of the final score.

<Classes>
	Game()			: Draw game scene.
	MainMenu()		: Show the Main menu page with game title and buttons(play, 				  option, how to play).
	CreditsScreen()	: Show the How to Play page with rule of the game and credits.
	OptionsScreen()	: Show the Option page with sound on/off button and chance 					  the character's color button.
	GameOverScreen(): Show the game over contents such as text of the final score 					and game over text.
	Button()		: Create the buttons. If the mouse is over the button, the 					  buttons' color would be brighter than default.
	Player()		: Draw, move, stop the character.
					  this.x += this.Xspeed;
					  this.y += this.Yspeed;
					  this.Xspeed = 5;
					  this.Yspeed = 5;
	Vec2()			: Same as createVector in p5.js.
	Balls()			: Create the Obstacles(balls) using vector.
					  this.bx = createVector(x, y);
					  circle(this.bx.x, this.bx.y, this.bs);
	Life()			: Show the left life and including googly eyes.
	Score()			: Show the current score while player is alive and final 					  score when the game is over.

<Arrays>
	balls1 = [] / balls2 = []
		Make the black balls. Update in function Black() and draw in function Drawballs().