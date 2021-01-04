# The-Mental-State
  The website disccuses several aspects of our projects. Topics include:
   ## Project Scope
   ## Background
   ## Data/Files Used
   ## Methods
   ## Threshold
   ## Results
   ## Discussion
   ## Next Steps
   
     The HTML code for the website can be found in the index.md
     There are several images uploaded, however the images used for the data are 
     
   ## Official Image 1
   ## Official Image 2
   ## Final Image 5
   ## Final Image 6
   ## Final Image 7
   
     There is an embeded theme within the site, and can be found in _config.yml
     
   ## Jekyll-theme-cayman
  
## THE CODE FOR THE IMAGES AND GRAPHS

 ## Loading The Data
   The code extracts the Facebook group names from the your_group_membership_activity.json file in the groups folder. It loads the posts and comments in groups from the    your_posts_and_comments_in_groups.json file in the groups folder. It loads the reactions within the groups from the posts_and_comments.json in the likes_and_comments
   folder.
   
 ## Extracting Group Names And Number Of Reactions, Comments, And Posts
    The code first extracts the group names. To do this, the code searches for the first occurrence of the string ” in “. The group name is found by extracting the rest 
    of the string following the first occurrence of “ in ” and excluding the last period. The likes and reactions are found by using regular expressions to see if a   
    group name existed in the title. The comments and posts are found by searching for if the variable group exists in the data set.
    
 ## Plotting Results
  Once the code has these comments, posts, and reactions and their respective timestamps, the code counts the number of these per month. With the count of these group 
  interactions aggregated by month, the code looks for the first date that has a count above 25% of the maximum count (our threshold). The code then extracts all counts   occurring after this first date. The code plots these counts against the month on a line graph. It adds a regression line to help capture the general trend.
  
## Plotting Friend Tags
  The code then parsed through all the comments and marks which comments contain a friend name in them - i.e. the user tagged a friend in that comment. The code groups 
  them by month and looks for the first date that has a count above 25% of the maximum count (our threshold). The code then extracts all counts occurring counts 
  occurring after this first date. The codeplots the number of friend tags against month on a line graph. It adds a regression line to help capture the general trend.

## Group Name Sentiment Pie Chart 
  The pie chart for group membership activities represents the proportion of positive, negative and neutral groups that the individual is a member of. The TextBlob   
  library is used to perform Sentiment Analysis of Group Names and get the polarities of each group name. The groups are further segregated into positive, negative and 
  neutral groups if the polarity is greater than 0, lesser than 0 and equal to 0 respectively. It is seen that the number of neutral groups is more as compared to the 
  positive and negative groups. This is because sentiment analysis requires large amounts of text data and the short names of groups is not enough. Thus, this analysis 
  is not included in the final project.






