# Team01-EgglyBuddies
Created by the Sunnyside Collective ☀️🍳\

Note to players: delete the ```game.json``` file to restart the game from the initial cut scene.

### Milestone 4 Submission:
Note that the milestone 4 submission form is titled MilestoneSubmissionForm_M4.pdf and is located alongside the Milestone 1, 2, and 3 submission forms in the `/docu/` folder. 

We are using 1 grace day and submitted all the relevant code for M4 by Tue Dec 5.

**Sources:**
- Sky assets: https://free-game-assets.itch.io/free-sky-with-clouds-background-pixel-art-set 
- Food assets: https://alifdoll.itch.io/pixel-food-asset
- Trailer music: https://happysoulmusic.com/audio/getting-it-done-by-kevin-macleod-mp3/ 
"Getting it Done" Kevin MacLeod (incompetech.com)
Licensed under Creative Commons: By Attribution 3.0
http://creativecommons.org/licenses/by/3.0/


**Creative Components (3 basic and 1 advanced):**
- Cut scene + story telling
  - Added in `world_system.cpp` and `mail_system.cpp`
  - Includes an intro with a story-telling component to explain what is happening in the game to the user 
- Enemy group behaviour AI (advanced)
  - Backyard minigame - `backyard_game_system.cpp`
  - Try to shoot and kill enemies that are moving around you
  - enemies will dodge projectiles and block projectiles (group behaviour) for other enemies that are on their last life
  - Enemy AI - `enemy_state_machine.cpp`.
- External library freetype
  - Added to `text_rendering.cpp` and the `CMakeLists.txt` file
  - Imported this external library to allow custom text rendering (instead of needing to hand draw all images with text)
- Game Balance
  - See attached PDF document `Milestone4.pdf`.

---


### Milestone 3 Submission:
Note that the milestone 3 submission form is titled MilestoneSubmissionForm_M3.pdf and is located alongside the Milestone 1 and 2 submission forms in the `/docu/` folder. 

We are using 1 grace day and submitted all the relevant code for M3 by Tue Nov 21.

**Kitchen Mini-Game:**
- Entry Points
  - Click on the fridge, click on the pan to get to the pancake minigame
- Pancakes fall onto the plate and you need to stack them one-by-one
  - When you stack 10 pancakes you win
- If you miss 5 pancakes you lose
  - Winning reduces buddy hunger


**Creative Components (2 basic and 1 advanced):**
- Reloadability
  - Buddy’s status now is being saved in a JSON file,  it gets reloaded when the game restarts.
- Save_System.cpp
  - Sound Effects
  - In data folder, 2 new background sounds and 3 new sound effects were uploaded
    - Sourced from https://mixkit.co/free-sound-effects/ and https://pixabay.com/sound-effects/ 
- Particle systems
  - When plants finish growing, it has sparkles until picked up
  - render_system.cpp, particles.vs.glsl, particles.fs.glsl

---

### Milestone 2 Submission:
Note that the milestone 2 submission form is titled MilestoneSubmissionForm_M2.pdf and is located alongside the Milestone 1 submission form in the `/docu/` folder. 

We are using 1 grace day and will submit all the relevant code for M2 on Tue Oct 31.

#### Entry points
Improved Gameplay:

**Game logic:**
Different rooms have different things you can interact with using the mouse
- Backyard: click on seed plots to grow stuff, click on plants when they’re fully grown
- Bathroom: User can drag the shampoo and body wash to wash the buddy. The clean will reduce the tiredness of the buddy.
- Bedroom: Turn on/ off the light to put buddy in bed and click on its dream bubble to play the dream minigame
- Dream Minigame: simple treadmill-style jump over obstacles to earn points minigame
- Kitchen: User can slice the apple, open the fridge
- Animation:
  - Spritesheet component: Spritesheet animation system implemented where it sequentially renders each frame of the given png using a given dimension, startpoint, and speed of animation, and a boolean flag indicating whether to loop through the animation or play it once.
- Assets:
  - Entry point: data/textures
- Mesh-based collision detection:
  - Entry point: mesh_collision.cpp and mesh_collision.h
- User tutorial / help:
  - Entry point: UserHelp component
  - Click on Help button in top left corner and it displays and explanatory image


Creative Components (2 basic or 1 advanced):
- Basic physics: gravity effects 
  - Apple
- Camera Controls
  - Camera component


---

### Milestone 1 Submission:
All entry points to each of the implemented features are listed below, and each feature is explained briefly. The proposed development plan and how our submission is aligned to it is detailed in `docu/Milestone1.pdf`, along with the game design documentation (in the form of an ECS diagram displaying the interactions between entities and components).

The `MilestoneSubmissionForm.pdf` is also included in the `/docu/` directory.  

##### Assets
- Mountain background:
[Image by stockgiu on Freepik](https://www.freepik.com/free-vector/arcade-game-world-pixel-scene_4815143.htm#query=pixel%20art&position=2&from_view=keyword&track=ais)
		 	 	 							
##### Textured geometry 
- Entry point: data/textures/
- Pictures drawn by hand.

##### Basic 2D transformations
- Entry point: world_system.cpp, world_init.cpp
- Rendering textures onto window screen.

##### Key-frame/state interpolation 
- Not done

##### Keyboard/mouse control
- Entry point: world_system.cpp → keyInputUpdate()
- Right/Left arrow keys move creature side to side.

###### Random/coded action
- Entry point: world_system.cpp -> on_mouse_button, updateMail(elapsed_ms);
- Random interval timer that triggers an event: You receive mail. Click on mail icon to receive a postcard with a random message on it.

##### Well-defined game-space boundaries 
- Entry point: physics_system.cpp and Boundary component
- Entities have a boundary component that they cannot leave.

##### Simple collision detection & resolution (e.g. between square sprites)
- Entry point: physics_system.cpp
- After colliding with wall, creature can no longer continue moving in that direction.

##### Parallax background 
- Entry point: world_system.cpp → updateClouds;updateMountainMove
- Window background: moving mountains and clouds that go by at different speeds.
