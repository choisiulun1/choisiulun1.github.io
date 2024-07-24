## Generating GIFs

To generate GIFs using the FORM program, you can utilize the `Gif2Gif` class from the `mylib` module. Here's a detailed guide on how to do it.

#### Step-by-Step Guide

1. **Import the Gif2Gif Class**
   
   First, you need to import the `Gif2Gif` class from the `mylib` module.

   ```python
   from mylib import Gif2Gif
   ```

2. **Initialize the Gif2Gif Object**
   
   Create an instance of the `Gif2Gif` class by passing two parameters: `r_width` and `fps`.

   - `r_width`: The actual width of videos.
   - `fps`: The frames per second for the GIF.

   ```python
   gifCreator = Gif2Gif(170, 10)
   ```

3. **Run the GIF Creation**
   
   Use the `run` method of the `Gif2Gif` object to generate the GIF. This method requires two arguments:
   
   - The directory where the video files are located.
   - The directory where the generated GIFs should be saved.

   ```python
   gifCreator.run("./videos", "./gif")
   ```

> Pls put all the videos you need to generate inside the videos folder.
> Important!!!: Don't modify the folder path , unless you know what's going on. There is no robust handling for changing the folder path.
> 
> Important!!! : All the videos are generated under same parameters like fps and r_width in a batch manner. No api for individual video generation while using different parameters.
#### Example Code

Here's the complete example code for generating GIFs:

```python
from mylib import Gif2Gif

# Initialize the Gif2Gif object with the actual width and FPS
gifCreator = Gif2Gif(170, 10)

# Run the GIF creation process
gifCreator.run("./videos", "./gif")
```

## Calculation of Stat

```python
def get_all_stat(self):  
    self.get_move_frequency()  #Cadence
    self.get_move_distance()   # Step_legnth
    self.get_swing_speed()   
    self.get_swing_angle()  
    self.get_waist_slope()  
    # self.get_flight_time()  
    self.get_head_stability()  
    self.get_back_swing_distance()
```

This function is used to calculate all the stat. This function is under Calculator Class in mylib.py


## Cache System
No cache anymore. The cache folder should be empty. *Don't delete the cache folder* , it's useless, for safety reason though.

## Analysis Page

![[Pasted image 20240708211112.png]]
It's supposed to see folder inside graph. The folder name is video name. For Example, `v2.mp4` 's graph is inside `v2` folder.


![[Pasted image 20240708211220.png]]
Suppose you upload `v2.mp4` in the run analysis , The page will grab the graph inside v2 folder automatically.
> Important!!!!: Make sure you use gif.py to generate the gif and graph first before you upload the v2.mp4 , which is the v2 graph should be already there when you upload the v2.mp4. This page won't do anything about calculation or generating graph since it takes a lot of time. You should do the batch generation first before you use this page. There is nothing done with the uploaded video. This page simply grab all the graph and .gif file when you click the import video button. 
> **It's fake and just for demonstration**


## Webpage

If you want to modify the logic of webpage , check `main.py`.
If you want to modify the html , javascript , css stuffs , check `templates` folder.
