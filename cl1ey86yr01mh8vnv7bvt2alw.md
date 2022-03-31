## Quizzify - Play unlimited quizzes with your friends for free!! 🔥

## A bit about myself

%[https://media.giphy.com/media/Nx0rz3jtxtEre/giphy.gif?cid=ecf05e47sgg8gnzk141a100oyb0435ybwosd44e394p09o0j&rid=giphy.gif&ct=g]

Hello There 👋. I am Vaibhav. I am an Android Developer, currently an engineering student 👨‍🎓 with a knack towards software development and everything about technology. I am very excited to share my journey building this project for [Hasura x Hashnode Hackathon](https://townhall.hashnode.com/hasura-hackathon)

# **Play unlimited Quizzes with you friends for free on ** Quizzify.

## Video Introduction 📹

This is a small introduction video about Quizzify.

%[https://youtu.be/rD2-MplbPBU]

## A bit of background


I was just scrolling through Hashnode and the article of Hasura x Hashnode hackathon came on my feed. I felt I should give a shot at it.

Then I started brainstorming about what to build and then I got reminded of my school days when I used to challenge my friends in quiz, we had lots of fun playing it, we all would go through quiz books and videos and prepare, this was very fun to play and by playing this we improved our chances to qualify for the school quiz competition. Then I thought _"Why not make a quiz game for people to play and get 
some more general knowledge"_ . So, then I started to build a mobile quiz game which can be played with friends in real time, which would be a good time-pass as well as would help people gain some more general knowledge while enjoying the game.

**Quizzify not just a game which helps people have fun with their friends and pass their time, but also helps people gain more general knowledge whle having fun playing it.**

**Quizzify has a clean and simple user-friendly interface which makes it easier for people of all age group to use it**

**Quizzify has various quiz categories, a lot of community made quizzes as well as instant quiz which is fetched from a public API**


## Quizzify - Play unlimited quizzes with your friends for free🔥


### UI Designs

Before starting with the project I started with the UI designing, and this is one of the toughest part in building a project. Mostly selecting the right illustrations and icons.

These are the some of the designs I made in Adobe XD.

![UI=Designs](https://cdn.hashnode.com/res/hashnode/image/upload/v1647774686361/WMBsoG44P.png)

### App Features

- **Onboardng** - Quizzify has a beautiful user onboarding process.
- **User Authentication** - Supports email based as well as Google authentication
- **Home** - Home screen shows the top 5 popular community quizzes, option to start an Instant quiz and to join an exisiting quiz game using invite code.
- **Communtiy** - Shows list of all community made quizzes with option to search and filter based on category. It also allows user to create a new community quiz.
- **Create Quiz** - Users can create quizzes and contribute to the Quizzify community.
- **Favourites** - It list all the quizzes the user has marked as favourite.
- **Profile** - Shows user's profile.
- **About** - Shows information about the app like its version number and more.
- **Quiz Detail** - Shows details of the quiz select and option to start game with friends as well as solo.
- **Game Screen** - Screen where user plays the quiz in real-time with their friends

### Insights into the app 🔎


![Quizzify - slides.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693160293/_0ttFtYYA.gif)

**Quizzify** has a sleek, modern looking minimalistic UI which makes it easy for people of every age group to use. 🔥



![Untitled design.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693198971/kw6umv442.gif)


**Quizzify** has a easy and simple user onboarding process. 😁


![Untitled design (1).gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693225605/_BGxAc1EX.gif)

**Quizzify** uses Firebase for authentication. It supports email-based authentication as well as Google authentication with upcoming support for Facebook auth.


![Untitled design (2).gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693216108/kpEIF8CVx.gif)


Select whatever quiz you want to play and have fun time with your friends and gain some more general knowledge while playing.



![Untitled design (3).gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693273748/tCaskC2u2.gif)

Play quizzes in realtime with friends with live rank and score tracking and enjoy a simple and easy game experience.



![Untitled design (4).gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1647693291275/TgxISULu6.gif)

You can even create quizzes of your own and play with friends. So go on, create quizzes of your own and contribute to the Quizzify community.

  
### Technical details 

- Quizzify uses Firebase for user authentication, it supports email based authentication and Google authentication
- Quizzify uses Hasura Cloud's PostgreSQL as it's primary database.
- Quizzify uses Hasura's GraphQL API to access the database and is much easier to work with compared to a REST interface.
- Quizzify has full offline support, it uses Android's ROOM database for caching all data offline.
- Quizzify is made using Kotlin and following Modern Android Development practices.
- Quizzify uses Kotlin Coroutines and Flow to handle all asynchronous tasks.
- Quizzify uses all Jetpack libraries and follows MVVM architecture. It also has a G.O.A.T rating in Android's  M.A.D scorecard.
- Quizzify's code follows all the best practices and software development principles like SOLID which make it a very good learning resource for beginners as well as for people looking to improve their software design skills.
- Quizzify's code is properly linted using Ktlint.


![summary.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1647777105663/Ua8fDcln2.png)

### Tech Stack
 
 - Android 
 - Kotlin
 - Android Jetpack Components
 - Android Architecture Components
 - Firebase
 - Hasura

### Hasura GraphQL
  
#### **These are some of my GraphQL queries**

##### This is how I am fetching all quizzes

```graphql
query GetAllQuizzes {
    quiz {
        category {
            id
            image
            name
        }
        createdBy
        createdByUserId
        description
        id
        name
        questions
        votes
        timestamp
    }
}

```

##### This is how im saving quizzes

```graphql
mutation SaveNewQuiz(
    $id:String,
    $categoryId:String,
    $createdBy:String,
    $createdByUserId:String,
    $description:String,
    $name:String,
    $questions:String,
    $votes:Int,
    $timestamp:String
) {
    insert_quiz_one(object: {
        id: $id,
        categoryId: $categoryId,
        createdBy: $createdBy,
        createdByUserId: $createdByUserId,
        description: $description,
        name: $name,
        questions: $questions,
        votes: $votes,
        timestamp:$timestamp
    }){
        id
    }
}
```

##### This is how I'm observing games.
``` graph
subscription ObserveGame($gameId: String!) {
    game_by_pk(gameId: $gameId) {
        gameId
        gameState
        hostId
        inviteCode
        players
        quiz
        timestamp
    }
}
```

### Challenges I faced and how I solved them ✅

**Developing a software is full of challenges and twists and turns.**

- Working with GraphQL was a bit tricky in the beginning as it was the first time I tried something other than a REST Api. Setting up the GraphQL support in Android using Apollo-Kotlin was a bit tricky as well.
Very thanks to Apollo Kotlin and Hasura documentation, which made the integration easy.
  
- Handling the real-time quiz game feature was quite difficult to manage, it was also my first time making an app which has some real-time feature. After few days of scratching my head I finally figure out how to handle all states of the Game, like one of the players finished game, one player has moved up in the leaderboard, player leaving the game, host leaving the game which should end game for all users, and many more such states. 🎉


### Future Improvements 🌟

- Adding more features like adding friends in app so users can directly invite friends rather than sharing the invite code with them.
- Add Chat support so users can chat while playing Game.
- Better handling of the unexpected errors than can occur while game is being played, like sudden loss of internet etc.
- Making the app completely offline ready so users can play quiz alone in offline mode and the result gets uploaded to the server as soon as internet comes using Work Manager API in Android.
- Improve the EXP ranking system in app and add some Global leaderboard kind of feature.
- Fine tuning the UX part of the app.


### Source Code 👩‍💻

If you want to have a look at the source code of the app, here is the link to the Github Repository 
[Quizzify](https://github.com/Vaibhav2002/Quizzify) 

You can download the latest version of Quizzify from https://github.com/Vaibhav2002/Quizzify/releases/tag/v1.0.0

**Feel free to contribute to Quizzify and raise issues if you find any.**


### Vote of thanks 👏

I would like to thank **Hashnode Discord server** for providing such a good support. Special thanks to the members of **Hasura** for helping me fix some issues that I faced while integrating Hasura.

---

## If you like my projects and want to support me to build more cool open source projects
  
<a href="https://www.buymeacoffee.com/VaibhavJaiswal"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=VaibhavJaiswal&button_colour=FFDD00&font_colour=000000&font_family=Comic&outline_colour=000000&coffee_colour=ffffff" />
</a>

---

%[https://giphy.com/gifs/reaction-jeff-bridges-nadine-QM5lHSyFjz1XW]