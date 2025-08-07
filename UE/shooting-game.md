//making a shooting game briefly

//a basic cube is a pawn for player

<img width="1468" height="815" alt="image" src="https://github.com/user-attachments/assets/3526a7f8-f4eb-4441-9110-d49a84145c35" />

//BP_Player

//from the beginning to player moving part (for now! 25.08.04)


<img width="1081" height="312" alt="image" src="https://github.com/user-attachments/assets/fa6bf0f9-2101-4629-a27b-f45059133902" />

//BP_Fire

//player's bullet (goes only forward)


<img width="1518" height="288" alt="image" src="https://github.com/user-attachments/assets/7b29b1ce-7273-4ee8-9d15-cefb17cdbcc4" />

<img width="955" height="333" alt="image" src="https://github.com/user-attachments/assets/3bbf1576-a9fc-4797-870c-d82258394ad9" />

//BP_Enemy

//spawn enemy (only 35% of them moves to the direction of the player, others move just straight to the opposite side)(trace rate = 0.35)


<img width="1232" height="262" alt="image" src="https://github.com/user-attachments/assets/3220343a-958f-40dc-a6cf-4d23dd42db92" />
//BP_Enemy Factory

//spawn enemy constantly, in random direction

//there's a cube(for now) as a player and it fires bullet when you left click, 5 enemy factory that constantly generates enemy(which is also cube for now)
//collision part would be updated tomorrow!!
//25.08.05

<img width="400" height="685" alt="image" src="https://github.com/user-attachments/assets/530bd0c9-65d5-4557-88d3-dcd319423310" />
//collision setup of BP_Player

//No additional blueprint scripting


<img width="404" height="658" alt="image" src="https://github.com/user-attachments/assets/9ceab432-e8fc-4bd5-9a82-aff32c17eb57" />
//collision setup of BP_Enemy

<img width="1129" height="330" alt="image" src="https://github.com/user-attachments/assets/f53e4290-cb58-480b-bdd9-af736e649a95" />
//additional blueprint scripting for destroying player, bullet, enemy itself, after specific collision happens

<img width="1845" height="894" alt="image" src="https://github.com/user-attachments/assets/9edacf7c-77e9-4c47-b8e4-5bc6ca09fb99" />
//spawn BP_KillZone to delete object which got out of the frame (Bullet, Enemy)

<img width="513" height="171" alt="image" src="https://github.com/user-attachments/assets/b437ec37-5813-42f3-bed7-8de371d64ef0" />
//overlap with enemy or bullet would delete them
//25.08.07
