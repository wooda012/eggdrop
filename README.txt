Colin Woodard <wooda012@cougars.csusm.edu>

Source code and APK found at http://github.com/wooda012/eggdrop

Major Features/Screens:
	-Login Screen: gets permission to use microphone audio, grabs username from username
		includes navigation to game and highscores, maintains previously entered username 
		if returning from highscores
	-Game Screen: Holds a gameView object, which has a thread handling updates to the game
		This screen will be described by the features later in the README
	-Highscore Screen: Maintains a list of the top 10 scores achieved on the device. Only a local
		table, no online database
		
Optional Features:
	-Device Shake (6 pts): During the game, a red line obstacle will occasionally appear that covers the whole
		screen, making it unavoidable by tilt control. By detecting device shake with
		accelerometer data, the obstacle can be avoided. (seen in GameView class)
	-Accelerometer (8 pts): The user's main control of the egg is achieved by using the device accelerometer
		to detect device tilt. If the tilt is substantial enough then the egg will move across the screen
		accoring to the direction and severity of the tilt. This is how the user avoids the game's
		main obstacles (seen in GameView class)
	-Microphone/Audio Management (8 pts): Similar to device shake, a green line obstacle will occasionally appear that
		covers the whole screen, making it unavoidable by tilt control. By recording the phone's microphone,
		and listening to the amplitude of the input, the game detects if a noise (that is louder enough) has occured,
		and if so it will delete the noise obstacle and it will be avoided. (seen in GameView class and DetectNoise class)
	-Data storage using file read/write or data serialization read/write (8 pts): internal file system is kept
		to maintain the highscores page. Data is formatted in a simple plaintext format where each line has two
		tokens, a name and a score. The app will initialize this file with every line reading (None 0.0), and
		will write new high scores to this file, and has the ability to clear highscores and start fresh.
		(HighScoreEntry.java, HighScoreTable.java, HighScores.java)

Testing Methodologies:
	This app was developed on an LG G6 phone, and most testing took place on that device. Final build was also
	tested on an LG G7. Multiple students were asked to playtest the game to ensure it was not too hard or easy.

Usage:
	No special info is needed to run the app, but the app will need to be run on an actual android phone
	due to the nature of the features (tilt control, device shake, microphone input).
	
Lessons Learned:
	I learned a lot about how to find and use sensor data when developing an android app. It can be very confusing
	on how to interpret the data retrieved from sensors and make use of it. In addition, figuring out how to detect
	noise was difficult, as most resources online only show you how to record it and not process it in realtime.
	I learned a lot about runnables and threads, because a game needs many different things happening at consistent framerates.
	I also learned that asset design is really not my forte, and it would be better to have someone more artistically talented on
	my team to handle that aspect
	