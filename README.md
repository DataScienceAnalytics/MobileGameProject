# MobileGameProject
A mobile game data science project 

<br> Author: Raymond Peng 
<br> Contact Info: raymond.peng@mail.mcgill.ca
<br> Linkedin: www.linkedin.com/in/raymond-square-enix/

<b>Stakeholder</b>:
   - Game designer

<b>Objectives</b>:
   - Identify potential paid users from new players who finished the onboarding tutorial
   - Apply data science techniques to suggest different prices & offers for those potential paid users
   
<b>Assumptions</b>:
   - The onboarding tutorial has <b>4 phrases</b> and each phrase allows players to enjoy a unique playstyle of the game
   - The experience points a player can accumulate from each phrase of the tutorial <b>is not fixed</b>. The amount depends on the performance and some optional activities during each phrase of tutorial
   - The experience points accumulated during tutorial can <b>reflect a user's engagement levels</b>
   - Experience points accumulated during each tutorial phrase will be tracked and recorded <b>at the completion</b> of that tutorial phrase
   - Metrics game_stats_xp, game_stats_xp1, game_stats_xp2, game_stats_xp3 represent the experience points a player accumulates in tutorial phrase0/1/2/3 correspondingly
   - All the stats_xp metrics mentioned above are <b>independent</b> from each other. They are not cumulative based on previous tutorial phrase but the exp points collected during the corresponding tutorial phrase
   - As last phrase of tutorial completed, the player need to collect some rewards and confirm to proceed to the main menu in order to complete the tutorial. <br>If he/she quit without collecting and proceeding, the tutorial will be considered as incomplete. 
   - All the user metrics under ka_devices and ka_users tables except for 'total_spend' will be <b>known and tracked</b> once a new user <b>opens the game for the first time</b>
   - Assume the game designer wants to give different prices & offers to new users who finished the tutorial based on their engagement levels which are reflected by the exp_stats related metrics
   
<b>Solutions</b>:
   - Identify potential paid users from the new users who finished tutorial with a <b>classification model</b> based on features that are known by the end of tutorial
   - The classification model should focus on <b>recall ratio while keeping a good accuracy</b> since we want to identify as many actual paid users as possible
   - <b>Segment users who completed the tutorial</b> into different tiers based on their tutorial engagement levels which are reflected by <b>stats_xp variables</b> using <b>clustering</b>. Present the user behaviors under each tiers to game designers and discuss what prices or offers should be given correspondingly. <br>The cluster model can be used to label future new users to a tier
   - <b>Deploy the models</b> mentioned above into production after discussion with game desginer and the data science team (deployment process will not be included in this notebook)
