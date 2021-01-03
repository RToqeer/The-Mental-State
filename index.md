<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Project Scope</h1></u>
    
    <p>
      In this project, we focused on analyzing users’ general mental state from their social interactions, particularly in groups (communities).
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
     Mental state can be predicted from social media data by analyzing the user’s behavior and how it changes over time. According to a study , whether internet interaction predicts changes in users’ well-being depends on how the users use it, such as the sites they visit, and who they interact with.
      </p>
      
      <p>
       Social behavior is one indicator of mental state. A change in social behavior can indicate if they are experiencing changes in mental state. Numerous studies [2-5] have shown links between social interaction and mental wellbeing. In addition, recent studies [6-5] also show that some health outcomes, including mental state & emotions, can “spread” through social networks. Therefore, our project focuses on quantifying these social interactions, particularly within groups/communities and friends.

      </p>
      
      <p>
        <b> Why Groups? </b> Groups are akin to communities, which consist of people bonding over similar interests. This shows that groups are established social networks. There are two types of interactions that can happen: bridging social capital and bonding social capital [8]. General actions in these communities represent bridging social capital. Meanwhile, when a user tags others within those groups, it represents a bonding social capital, because it confirms that the action is indeed an act of friendship.

      </p>
      
      <p>
        <b>Why Not Messenger? </b> Messenger is not the best indicator of friend interactions. Instant messages have lots of different purposes that may not reflect friendship interactions, such as formal club group chats, organizing events. Regular chats between friends are just a small part of how Messenger is used. 

      </p>
  </body>  
   <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>  
  <body>
    <u><h1>Methods</h1></u>
    
    <p>
      <b>First plot - Reaction, Comments, Posts In Groups</b>
    </p>
    
    <ol>
     <li>The number of reactions, comments, and posts inside groups were counted and analyzed to see how they changed over time.</li>
     
    <li> We gathered the names of the groups the person was in at one point of time by extracting all the groups from your_group_membership_activity.json. This file
    
    indicates when a person joined or left a certain Facebook group. The group names from this indicated to us the types of the groups the person has been involved in 
    
    (either currently or at one point in time).</li>
    
    <li>Afterwards, we extracted all the posts and comments made by the user within groups from the your_posts_and_comments_in_groups.json file. We aggregated this data by month and counted how many posts and comments a person had in any group at a certain month.</li>
    
    <li>Furthermore, we looked into post reactions (like, love, haha, angry, sad, etc.) in groups. The posts_and_comments.json files reactions for all posts (both inside and outside groups), so we searched for the keyword “in” in the title to see if that reaction was in a certain group or not. We then aggregated this data by month and counted how many reactions a person had in a group at a certain month.</li>
    
    <li>The number of comments, posts, and reactions per month were then added and plotted using linear regression to capture the overall trend of that user’s behavior.</li>
    </ol>
    <p>
      <b>Second plot - Friend Tags Within a Group</b>
    </p>
    
    <p> We wanted to see how the number the user tagged a friend in a comment on a post in a group changed over time.</p>
    
    <ol>
    <li> We arsed through all the comments to look for names that are in the user’s friends list. If a friend name pops up in a comment, then that comment is counted as having a friend tag in that comment.</li>
    
     <li> We then aggregated the number of friend tags by month and counted how many friend tags did the user do per month.</li>
     
     <li>The overall trend of behavior was modeled using linear regression.</li>
     </ol>
     <b>Data Used:</b>
     <ul>
     <li>groups > your_group_membership_activity</li>
     <li>groups > your_groups</li>
     <li>groups > your_posts_and_comments_in_groups</li>
     </ul>
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
    <img src = "Final Image 1.png">
    <img src = "Final Image 2.png">
    <p>Red line = Regression Line = Trend over time</p>
    <li>Number of friend tags within a group over time (Bonding Social Capital)</li>
    <img src = "Final Image 3.png">
    <img src = "Final Image 4.png">
    </ol>
  </body>
  <body>
    <p>
    <b> Disclaimer </b>
    </p>
    
    <ol>
     <li>This is just ONE way to predict user’s mental state and how they change over time.</li>
     <li>It is best to combine this insight with other data analysis for a better overview.</li>
     <li>Limitations exists:</li>
     <ul> Only works for English data</ul>
     <ul> Only works if someone joins the group</ul>
     </ol>
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
     </ul>
  </body>
</html>
