<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Project Scope</h1></u>
    
    <p>
      In this project, we focus on analyzing the general mental state of users based on their social interactions in online communities, specifically Facebook groups.
    </p>
    
  </body>
  
   <head>
    <meta charset="utf-7">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Background: Why We Do What We Do</h1></u>
    
    <p>
     Mental state can be predicted from social media data by analyzing how the user’s behavior changes over time. However, time spent on Facebook by itself is not enough to determine one’s mental state. According to a study, whether internet interaction predicts changes in users’ well-being depends on how the users use it - which sites they visit, who they interact with, etc.
      </p>
      
      <p>
       Social behavior is an indicator of one’s mental state, so change in social behavior can reflect change in mental state. Numerous studies have shown links between social interaction and mental wellbeing. In addition, recent studies have shown that some health outcomes, including mental state & emotions, can “spread” through social networks. Therefore, we sought to focus on these social interactions within Facebook groups.

      </p>
      
      <p>
        <b> Why Groups? </b> Facebook groups, which consist of people bonding over similar interests, are akin to communities. Facebook groups are very similar to established social networks. There are two types of interactions that can happen: bridging social capital and bonding social capital8. General actions in these communities - posting in the group, commenting on posts, and reacting to other group members - represent bridging social capital. Furthermore, when a user tags his personal friends within those groups, it represents a bonding social capital, because it confirms that the action is indeed an act of friendship.

      </p>
      
      <p>
        <b>Why Not Messenger? </b> Messenger is not the best indicator of friend interactions. The Facebook instant messaging platform is used for many different purposes that may not reflect actual friendship interactions. For instance, messenger is often used to expand one’s network, to organize events, or to even pass study notes for class. Regular chats between friends are just a small part of how Messenger is used. Given a certain conversation with a certain Facebook friend, it is not easy to determine if that Facebook connection is a true close friend or just an acquaintance or formal contact. On the other hand, a Facebook user would only tag his close friends in posts in a group. Thus analyzing a person’s Facebook tags in a group really does reveal his interactions with one’s true close friends on the platform.
      </p>
  </body>
  
   <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Data/Files Used:</h1></u>
    
    <ul>
      <li>groups > your_group_membership_activity.json</li>
      <li>groups > your_groups.json</li>
      <li>groups > your_posts_and_comments_in_groups.json</li>
      <li>likes_and_comments > posts_and_comments.json</li>
      <li>friends > friends.json</li>
     </ul>
  </body>
  
   <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Methods</h1></u>
  
     <img src = "Final Image 5.png">
    <p>
      <b>First plot - Reaction, Comments, Posts In Groups</b>
    </p>
    
    <ol>
     <li>We counted the number of reactions, comments, and posts inside groups and saw how they changed over time.</li>
     
    <li> We gathered the names of the groups the person was in at one point by extracting all the groups from your_group_membership_activity.json. This file indicates when a person joined or left a certain Facebook group. The group names from this indicated to us the types of the groups the person has been involved in (either currently or at one point in time).</li>
    
    <li>We then extracted all the posts and comments made by the user within groups from the your_posts_and_comments_in_groups.json file. We aggregated this data by month and counted how many posts and comments a person had in any group at a certain month.</li>
    
    <li>We also looked into post reactions (like, love, haha, angry, sad, etc.) in groups. The posts_and_comments.json file contains reactions for all posts (both inside and outside groups), so we searched for the keyword “in” in the title to see if that reaction was in a Facebook group. We then aggregated this data by month and counted how many reactions a person had in a group at a certain month.</li>
    
    <li>We then added the number of comments, posts, and reactions per month and plotted their total number per month. We used linear regression to capture the overall trend of that user’s behavior.</li>
    
    </ol>
    <p>
      <b>Second plot - Friend Tags Within a Group</b>
    </p>
    
    <ol> 
    <li> We also wanted to see how the number of times a user tagged a friend in a comment on a post in a group changed over time. </li>
    
    <li> We parsed through all the comments to look for names that are in the user’s friends list. If a friend’s name popped up in a comment, then that comment is counted as having a friend tag.</li>
    
     <li> We then aggregated the number of friend tags by month and counted how many friend tags the user had per month.</li>
     
     <li>We used linear regression to model the overall trend of the behavior.</li>
     </ol>
     
  </body>
  
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Threshold</h1></u>
    
    <p>
      We noted that many Facebook users had a period of relatively low activity in groups at the beginning of their Facebook usage.
    </p>
    
    <p>
    Ex: Kyle began using Facebook in early 2018 but was not active in online communities until late 2018. If we consider the data in its entirety, it looks like Kyle’s activity in groups increased over time despite there being an obvious decrease in group activity in the period of time Kyle after Kyle discovered Facebook groups.
    </p>
    
     <img src = "Final Image 6.png">
     
     <p>If we use the threshold, we can ignore the period of time before Facebook users discover and use these features and get a better sense of what that user’s group activity actually looks like.</p>
     
     <p>We can see a similar pattern in the friend tags in comments within Facebook groups:</p>
     
     <img src = "Final Image 7.png">
     
     <p>Our hypothesis is that when people first join Facebook, they interact primarily with their real friends. However, as times goes on and they explore and discover groups and online communities Facebook offers, they then join and interact with these Facebook groups.</p>
     
     <p>To account for this, we decided to set a threshold by taking a certain percentage of the maximum number of tags or reactions and finding at which month does the count surpass that threshold. This threshold represents when the user begins actively engaging in the online Facebook communities. We only look at the data after this date.</p>
     
     <p>The threshold allows us to focus on the actual behavior of the user, ignoring the period of when the user either did not realize groups existed or before users started actively engaging in online communities. Since both the interactions analysis and friend tagging analysis happen within groups, we applied this threshold to both analyses.</p>
     
     <p> <b> ** Kyle’s and sample data’s plot with thresholds * *</b></p>
        <p>In Kyle’s and Ethi’s data, utilizing a 20% threshold allows us to more accurately capture the change in the user’s behavior.</p>
  </body>
  
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Results</h1></u>
    
    <ol>
    <li>Number of interactions within a group over time (Bridging Social Capital)</li>
    <img src = "Official Image 1.png">
    <p> The number of Facebook group interactions in the data is decreasing over time. This indicates that this user is not interacting with other people on the platform as times goes on. This could mark a shift in the user’s Facebook usage (perhaps he watches more videos instead of scrolling through groups) or or time on Facebook (perhaps he simply spends less time on Facebook). This analysis, by itself, is not enough to fully determine one’s mental state, but if the user sees this graph and thinks about his own Facebook usage over this period of time, the user could determine if this does indeed accurately reflect a reduced amount of social interactions within communities on this platform.</p>

    <p><b>Red line = Regression Line = Trend over time</b></p>
    
    <li>Number of friend tags within a group over time (Bonding Social Capital)</li>
    <img src = "Official Image 2.png">
    <p>The number of friend tags in this data seems to be very volatile, but overall increasing over time. This indicates that this user is interacting with close friends in these communities at a higher and higher rate over time. This could indicate that the user is becoming closer and closer with his online friends and is bonding with them over similar things at an increasing rate. This analysis, by itself, is not enough to fully determine one’s changing bonding social capital, but if the user sees this graph and thinks about his own Facebook usage over this period of time, the user could determine if this does indeed accurately reflect an increasing closeness with his friends within these groups.</p>
    
    <p><b>Red line = Regression Line = Trend over time</b></p>
   
    </ol>
  </body>
  
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Discussion</h1></u>
    
    <p>
     Overall, these plots and these analyses alone cannot predict one’s mental state. However, counting the number of one’s interactions within Facebook groups - real online communities - and visualizing them to the user can allow the user to see these patterns and think about how they reflect on his or her own Facebook usage over the indicated time. </p>
     
     <p>There are many shortcomings of this study, and these analyses are by no means complete. More time would allow us to improve how we quantify one’s changing behavior within communities over time and more data would allow us to have baseline to see how one’s changing behavior in these communities compare to the average Facebook user.</p>

  </body>
  
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  
  <body>
    <u><h1>Next Steps</h1></u>
  
    <p>
    <b>For future development, we can do the following:</b>
    </p>
    
    <ul>
     <li>Categorizing the groups into subsets of groups (example: dog groups, meme groups).</li>
     <li>Determining the polarity of the groups (positive, negative, neutral), then doing text sentimental analysis on the posts & comments to see how the person’s sentiment within the groups changes over time.</li>
     <li>Combining this insight with other data analytics to create a more holistic overview of someone’s mental state</li>
     <li>Find a way to see how much time the user spends on Facebook daily, so we can see if the amount of time that person spends in Facebook groups (in communities) changes relative to his Facebook usage.</li>

     </ul>
  </body>
</html>
