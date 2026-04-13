To view the entire GitHub Repository for this project, click this link: [FULL AI PROJECT](https://github.com/SJUCS/ai-final-project-team7/tree/main) <br>

# AI Hospital Robot (Saint Joseph's University: CSC 362 Artificial Intelligence)
This project was completed with the help of a couple classmates and presented towards the end of the semester. Everyone attributed equally to the completion and testing/coding of the project. <br>
<br>
The project was divided into three phases: <br>
  1. Planning Phase - this is where we decidied what the hospital layout was going to be like, where the rooms were going to be located, and what each room's priority was going to be. Each room is assigned a priority in which the robot will go to the highest priority room first, then the next highest, etc. We also needed to find ways the robot "failed", so that it wouldn't move without knowing where it needed to go or if it was missing an inputted algorithm.
  2. Coding/Creating Phase - this is where we took on the physical aspects of the project, such as creating/cloning our repository into VisualCode, making the files, and coding everything.
  3. Testing - this last phase is very small, but this is where we tested everything to see if what we wanted to present worked. We troubleshooted along the way too.

## 1. Planning Phase:
Like every project, we needed to come up with a gameplan on how we were going to tackle this project. The two main things being how we would go about creating the layout for our robot to traverse and what we wanted it to look like (array, dictionary, etc.). We decided to use a **matrix**, we can also be described as a **2D Array**. Within this matrix, we have two values. **1** indicates a wall, while **0** indicates an open path. We created both a 30x30 **and** a 49x49 to test where the rooms were going to go and copy and paste that to the larger maze for presentation purposes. Emily was in charge of the maze, and hardcoded it in code to match the .jpg file of the actual maze. Both were pretty big images, so the picture of the maze is first with the hard-coded maze below it: <br>

<div style="display: flex; gap: 10px;">
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6bc562a2-e2df-4796-9483-64c3a3d5a582" />
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/22760186-4a6c-4105-9b1d-1eee3d749c1b" />
</div> <br>

Now that we have our maze, we can go about **Room Priority**. There are a total of 12 rooms within the floor plan of the hospital. Each room is given a priority (between 1 and 5, 5 being the highest priority). The robot can also be given any one of these twelve rooms, even multiple times in the same input file. We also gave each room a distinct color so the user can know where the robot is going and to give the GUI some vibrantness. These will all be included within the input file used to run the robot.
  - e.g If there are two rooms given in the input file, Oncology & Pediatric Ward, the robot will go to Oncology from where it's at first and then proceed to Pediatric Ward after reaching Oncolog. <br>
<br>
Now that we have these rooms and their cooresponding coordinates and colors, we needed to determine where they would go in the maze. More importantly, we need to know where the robot would travel if we gave it specific coordinates within the input file. So within (0,0) and (49,49), we assigned the travel point for the robot within each room. <br>
<br>
The priorities, coordinates, and colors for each ward are below (they are both dictionaries): <br>
<br>
<div style="display: flex; gap: 10px;">
<img width="173" height="282" alt="image" src="https://github.com/user-attachments/assets/66a1ee09-a16c-4357-aeba-5264fcbed544" /> 
<img width="250" height="305" alt="image" src="https://github.com/user-attachments/assets/9ce47d87-bfe5-4489-a458-a3ca2b53249f" />
<img width="218" height="306" alt="image" src="https://github.com/user-attachments/assets/89a0f730-0982-4d0a-83b3-95e16644ebbd" />
</div>

## 2. Creation Phase
Now that we have everything ready within the planning phase, we can go about creating the different files to both run the robot and bring up the GUI. But First will be the GUI to see of we can bring up the maze for visuals. <br>
One of my groupmates, Paul, took on the task of creating the file/code to create the GUI and visualize it. For this, he needed to do a couple of things: <br>
<br>
  1. We needed to read in the maze from the file in which it was created.
  2. Create a new file and functions to read in the maze and input files.
  3. Import a class to create a GUI with the selected maze of choice.

A snippet of code is below: <br>
<div style:"display": flex; gap px10;">

```
      def run_maze():
        # setting the root and title
        root = tk.Tk()
        root.title("Maze Visualization")

        # running the maze
        app = maze_class(root, maze_class.maze_data)
        root.bind("<KeyPress>", app.move_agent)
        root.bind("q", app.close_gui)

        root.mainloop()
```
Ths is the main code that runs, but you can see from this that Paul used **import Tkinter as Tk**, which is a common package used for creating GUI's. If you wish to see the rest of Paul's code, just so I don't overpopulate this page with the code, click [here](https://github.com/SJUCS/ai-final-project-team7/blob/main/src/display.py) <br>
<br>
With the GUI code now in place, we can implement the code needed for 




