# Intro

[Company Page](https://www.halfbrick.com/games/magic-brick-wars)
\
[Play on Google Play Store](https://play.google.com/store/apps/details?id=com.halfbrick.brickwars)
\
[Play on Apple App Store](https://apps.apple.com/us/app/magic-brick-wars/id1330800318)

**Made With: Unity, C#, Go**
\
**Contributions: Team lead, programmer, and designer for content updates**

*Magic Brick Wars* is where I spent most of my time while at Halfbrick. Shortly after I joined, there was a company-wide initiative to pivot to a cohesive subscription-based platform for all of our games rather than separate free-to-play experiences. As part of this initiative, teams were split up to start building the catalogue of games that would exist on the service, which mostly included polishing up old titles and integrating the Halfbrick+ SDK into them, which allowed users to play with 1 hour of guest time or create an account and access the game with a paid subscription. *Magic Brick Wars* needed a bit more work than other titles, though. It was initially released in 2019, and then was taken down after Amazon GameSparks shutdown in 2022, which the server was using. Once the strike team I was with was done with our first few titles, we were tasked with replacing the backend and transforming the economy from its free-to-play system, to a more premium one that would fit the subscription service.

For the backend we initially explored [Photon](https://www.photonengine.com/PUN), but later went with [Heroic Labs](https://heroiclabs.com/) since the company had previous experience with them. The team at Heroic Labs helped to port over all of the server code while we hooked it up client side, since the team was made up of mostly juniors. We started this work in August 2023, and after several challenge filled months, we made it over the line and released the game on Halfbrick+ in January 2024 to join about 20 other games. Now that our work was done, our current lead at the time went on to form another team to begin creating [Halfbrick Sports: Football](https://www.halfbrick.com/games/halfbrickfootball), since he was initally on loan to help us out. This left a void for the rest of my strike team and some other juniors in other teams after the first Halfbrick+ initiative was complete. Halfbrick was still looking to continue work on *Magic Brick Wars* to grow with the service, so I stepped up to lead after exemplifying promising leadership skills and high quality output in our previous projects.

Our goals with this new team were to bring back some of the features in the original version (after they were stripped away for scope in the re-release) and connect with the community to help shape the game in its new form as part of a subscription service. Throughout the next 1.5 years my team would go on to implement 7 content updates as we improved our skills and coordination within the company. For each of these updates I managed the team and was the vision holder for all aspects of design and architecture, collaborated with them to come up with ideas, and reviewed their code. We would regularly check in with our stakeholders to get approval and feedback on the features we wanted to implement. Development was a mix between updates we wanted to work on for player satisfaction, and updates that involved integrating new features from Halfbrick+ as it evolved (such as different tiers and economy experiments). Once we had the game in a good spot, we moved on to help build out features within Halfbrick+ itself for the next big initiative (unreleased as of February 2026, but here's a [sneak peak](https://www.youtube.com/watch?v=lts2-xGh2-s)!).

I learned so much while working at Halfbrick in general. I became a more skilled developer and collaborative team mate, improving both my code and communication in many areas. Unfortunately I can't share any code here to showcase how my skills have developed since *Wilbur's Quest*, but knowing what I do now I would completely rewrite it (and might actually take that on). At Halfbrick I worked with both old and new code bases, integrated with and improved many systems, including async operations and numerous C# features that I didn't know aobut, and overall learned how to implement clean and maintainable architecture. I hope that the content updates I outline here help to portray the obstacles my team and I have overcome to achieve great results that I can replicate on any project I become a part of.

\
Here are some images of what the current state of the game looks like (as of July 2025)
|![](README%20Files/current_battle_tab.jpg)|![](README%20Files/current_deck_tab.jpg)|![](README%20Files/current_profile_tab.jpg)|![](README%20Files/current_shop_tab.jpg)|
|-|-|-|-|
|![](README%20Files/current_social_tab.jpg)|![](README%20Files/current_stats_screen.jpg)|![](README%20Files/current_battle.jpg)|![](README%20Files/current_mine.jpg)|

You can skim through this video for what the game looked like in the original version (middle click to open in new tab)
[![Video](https://img.youtube.com/vi/OgddvahnWJ0/0.jpg)](https://www.youtube.com/watch?v=OgddvahnWJ0&list=PLuNyw_z6mVdUaNKTq1ejiy8ivb9WY5dgz&index=2)

# January 2024 Update | Stability and Economy Balancing

Right after release we started work on a quick patch to address some crashes that came up after the wider playerbase got their hands on the game. We also took in some feedback on how the progression felt compared to the original version, and while we were aiming for a different style, we tweaked the economy some more so that returning players could better transition to it.

# May 2024 Update | Card Balancing and Server Versioning

We started establishing a Discord community for veteran players of the original version to give focused feedback as we iterated on the Halfbrick+ version. We first addressed concerns with the meta getting stale in its later months and other card bugs or inconsistencies that the original team didn't get around to fixing. This mostly included stat/cost changes to over/under-powered cards. We also added a card update popup to show how cards have changed from their previous versions, where before players could only get that information from patch notes. We improved some of the UI for card stats themselves as well, adding more organized sections and stats that were previously omitted and only known through the backend. We were pretty happy to hear from players that we nailed the balancing on the first go and any deck became viable, and were excited to see some shake-up in prominently used cards.

Along with this, we added a versioning system to the server and its config files, since it was previously stripped out for the re-release. This was the first time I was introduced to Go and the server architecture. It took some getting used to, but pretty soon I was getting comfortable with it and understanding how the client communicates with things like player data storage and RPCs. Using this we also added a popup during the loading screen that could be triggered remotely at any time, which was useful for delivering messages to players about maintenance or updates, and included a force update blocker when there was a version mismatch.

|Card Update Popup|
|-|
|![](README%20Files/card_update_popup.png)|
