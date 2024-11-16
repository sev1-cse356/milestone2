# Documentation, how to start website

- cd into the github repo directory
- $docker-compose up --build
- $./smtp.sh

execute the docker container to see the videos </br>
- $ docker exec -it milestone2-express-1 bash

-----------

# Milestone #2 Description

1. Include all milestone 1 functionality and include the ones below

2. POST /api/like {id, value}
Allow a logged in user to “like” a post specified by id. value = true if thumbs up, value = false if thumbs down and null if the user did not “like” or “dislike” the video.
Response format: {likes: number} which is the number of likes on the post. This api should return an error if the new “value” is the same as was already previously set.

3. POST /api/videos {count}
Return information about videos that should be recommended to the user based on their previous like/dislike selections.
Use a collaborative filtering algorithm to identify videos that are likely to be liked by the logged in user by identifying other users that have similar like/dislike profiles and recommending videos that were liked by the other similar users.  If there are videos that should be recommended that have not been previously watched by the logged in user, they should be recommended.  If there are no videos that can be identified for recommendation based on collaborative filtering that have not yet been viewed by the logged in user, return random videos, first preferring those that have not been watched previously, and only falling back on random videos that have been watched previously.  
For an example of collaborative filtering, if videos with “id” 1 and 2 were “liked” by user A, and video with “id” 2 was “liked” by user B, then the system should recommend video “id” 1 to user B because users A and B have similar preferences, and user B is likely to enjoy video 1 because the user liked video 2.
Response format: {videos: [{id: String, description: string, title: string, watched: boolean, likevalue: boolean|null }]}, where videos contain ${count} number of videos.

4. POST /api/upload { author, title, video }
Upload a video to the site with title: title and author: author and video: is the mp4 file.
Response format: {id: string}

5. POST /api/view { id }
Mark video “id” as viewed by the logged in user.  This API call should be made by the UI on videos that were not previously watched whenever that video is first “played” for the user.

6. GET /upload
Expects an HTML page where videos can be uploaded from

7. GET /api/processing-status
Returns a list of uploaded videos for the logged in user.
Response format: { videos: [{ id: string, title: string, status: string }] }
where status can be "processing" or "complete", where “processing” indicates the file has been received, but not yet available for viewing.

8. All GET and POST responses must contain the header field X-CSE356 with the value containing the ID copied from the course interface.
If there is any error, you should reply with status code 200 and {"status": "ERROR","error":true,"message":"your error message"}, else respond with status code 200 and the response specified above.


-------------------


-------------

# Notes

- the m1.html is the http://130.245.136.73/mnt2/video/m1.html file that we made scripts to pull the videos from.

------------

Grading completed. Score: 10

Successfully added user: grader+O6xaZ8UPXo
/api/adduser ERRORs out when creating an account with duplicate credentials
Successfully verified users grader+O6xaZ8UPXo
Verifying user grader+gXRlcWTyMS with wrong key errors out
Recieved correct Header
Successfully logged into user grader+O6xaZ8UPXo = 1pts.
begin upload of videos
checking processing-status
Successfully upload video 530 = 0.5pts.
checking processing-status
Successfully upload video 531 = 0.5pts.
checking processing-status
Successfully upload video 532 = 0.5pts.
beginning basic tests
Successfully passed like test = 0.5pts.
Successfully passed view test = 0.5pts.
starting frontend tests
Login elements found.
Successfully logged in using frontend = 0.5pts
Found 10 thumbnail images at http://sev-1.cse356.compas.cs.stonybrook.edu
Thumbnail sources match expected pattern
Thumbnails are clickable. = 0.5pts
clicking
clicked
Successfully navigated to /play/20712217-uhd_3840_2160_30fps
Successfully paused and played video using pause/play buttons.
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Successfully paused and played video using pause/play buttons.
like and dislike buttons found!
Video Successfully Loaded
like and dislike buttons found!
Successfully scrolled down! = 0.5pts
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Successfully paused and played video using pause/play buttons.
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Successfully paused and played video using pause/play buttons.
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Video Fully Loaded
like and dislike buttons found!
Successfully scrolled up! = 0.5pts
Frontend Tests Passed!
basic tests passed! beginning to register other users and liking some videos
Added user: grader+gXRlcWTyMS
Added user: grader+sO8IzGs7ej
Added user: grader+hIOZ06u6YY
Added user: grader+pTtipcu6W-
Successfully liked videos on multiple users = 1pts.
found recommended videos and watched some of them! = 1pts
passed recommendation test = 1pts
sleeping to wait for uploaded videos...
waking up!
Fetching random manifest from student server...
Parsed DASH manifest.
Extracted video representation.
all representations correct in manifest
Successfully downloaded initialization segment OK
Successfully downloaded a media segment. OK
Student video fragment created.
Successfully downloaded thumbnail file api/thumbnail/530
Extracted frame from student video.
Successfully extracted frame for comparison.
Successfully extracted thumbnail for comparison.
Comparing randomly selected frames
Fetching random manifest from student server...
Parsed DASH manifest.
Extracted video representation.
all representations correct in manifest
Successfully downloaded initialization segment OK
Successfully downloaded a media segment. OK
Student video fragment created.
Successfully downloaded thumbnail file api/thumbnail/531
Extracted frame from student video.
Successfully extracted frame for comparison.
Successfully extracted thumbnail for comparison.
Comparing randomly selected frames
Correct video served.
Comparing randomly selected frames
Fetching random manifest from student server...
Parsed DASH manifest.
Extracted video representation.
all representations correct in manifest
Successfully downloaded initialization segment OK
Successfully downloaded a media segment. OK
Student video fragment created.
Successfully downloaded thumbnail file api/thumbnail/532
Extracted frame from student video.
Successfully extracted frame for comparison.
Successfully extracted thumbnail for comparison.
Comparing randomly selected frames
Comparing randomly selected frames
Successfully passed video test = 1pts.
