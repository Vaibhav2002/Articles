## Healthify - An app to track your daily water intake and sleep and boost your work efficiency - Auth0Hackathon.

## A bit about myself

%[https://media.giphy.com/media/Nx0rz3jtxtEre/giphy.gif?cid=ecf05e47sgg8gnzk141a100oyb0435ybwosd44e394p09o0j&rid=giphy.gif&ct=g]

Hello There 👋. I am Vaibhav. I am an Android Developer, currently a student 👨‍🎓 with a knack towards software development and everything about technology. I am very excited to share my journey building this project for [Auth0 + Hashnode Hackathon](https://townhall.hashnode.com/auth0-hackathon)

# Healthify **is here to help you track your daily water intake and sleep and boost your efficiency**.

## Video Introduction 📹

This is a small introduction video about Healthify.

%[https://youtu.be/QiP8NkIqVQs]

## A bit of background

I always felt that I am not drinking enough water daily because I am so busy at work that I never notice. I also used to feel that I am not getting enough sleep because I work late night. Having such lifestyle affects our health in the long run, it decreases our productivity and also weakens our health.

I used to feel like

%[https://media.giphy.com/media/mUeFDbJHvB2qCATSsq/giphy.gif?cid=790b761132797b194f6a62c84fe2848e8401937730333c0d&rid=giphy.gif&ct=g]


Then for a few days I started tracking my water intake and my sleep and I felt more active and productive. As developers we need to work a lot, we should try to keep ourselves healthy, this will help us get better at work too. It's a good thing to stay hydrated and get sufficient amount of sleep each day. 

Then I started to feel like

%[https://media.giphy.com/media/hokMyu1PAKfJK/giphy.gif?cid=ecf05e4782qgpgfum2axhchq1b7smnepqprf7mczv7tmz4bz&rid=giphy.gif&ct=g]

I was just scrolling through Hashnode and the article of Auth0 x Hashnode hackathon came on my feed. I felt I should give a shot at it.

Then I started brainstorming about what to build and then I though to make an app which helps people stay hydrated and maintain a good sleep amount.
But then I thought that - *"Why would people even use it , when they can just use a notepad app to note down their water intake and sleep"* 🤔

But people cant see an overview of how they much water they drank and hours they slept each week and see statistics of it. Healthify also has a XP based ranking system which will drive people to meet their daily goals hence making it their habit to drink sufficient amount of water and get good sleep.

**Healthify not just helps people to track their water intake and sleep, but also shows you a detail view of water intake and sleep in the last week. Healthify also has a ranking system which will drive users to meet their daily goals to compete hence making it their habit to drink water and get enough sleep**

**Healthify has a clean and simple user-friendly interface which makes it easier for people of all age group to use it**

**Healthify reminds you to drink water by sending a notification after 1 hour of your last tracked water intake**


## Healthify - Track your daily water intake and sleep and stay fit🔥


### UI Designs

Before starting with the project I started with the UI designing, and this is one of the toughest part in building a project. Mostly selecting the right illustrations and icons.

These are the designs I made in Adobe XD


![designs_light.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629895975000/AmAPwt2ly.png)


![designs_dark.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629896041572/vDJM-adVd.png)


### App Features

- **User Authentication** - Allowing users to login and register using auth0.
- **Dashboard** - There are two dashboards for sleep and water. It shows the amount of water drank and hours slept and also logs for each.
- **Add Water** - Selecting water amount to add in daily water list.
- **Water Drinking Notification** - Healthify reminds you to drink water by sending a notification after 1 hour of your last tracked water intake.
- **Add Sleep** - Selecting number of hours to add in daily sleep list
- **Statistics** - Shows statistics of water drank and hours slept within last week. 
- **Profile** - Shows user's profile.
- **Leaderboard** - Shows a leaderboard consisting of all users ranked based on XP points.
- **About** - Shows information about the app like its version number and more.

### Insights into the app 🔎

![light_dark.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891595035/lFtr0qsdm.png)

**Healthify** offers light as well as dark theme 🌓. So now you can use Healthify in whatever theme you like the most. 🔥


![slide-1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891610656/03R-2_RWj.png)


**Healthify** has a clean and sleek user interface which makes it easy for people of all age groups use it. 😁


![slide-2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891832777/d58rLRGpc.png)


**Healthify** uses Auth0 for authentication. It supports email-based authentication as well as Google authentication. **Healthify** also has a smooth user onboarding process.


![slide-3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891652934/nY2GKmQ9S.png)


Have a look at your daily water intake and statistics of your water intake in the last week.


![slide-4.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891720796/S3b1iziNY.png)

Have a look at your daily sleep 😴 amount and statistics of your sleep in the last week.


![slide-5.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629891854348/-4xlH9Np5.png)

**Healthify** has a XP based ranking system which ranks you among other users. XP can be gained by adding water and sleep. Having such ranking system in this app will make users compete and hence make it a habit of users to drink water and get enough sleep

  
### Technical details 

- Healthify uses Auth0 for user authentication, it supports email based authentication and Google authentication
- Healthify uses Firebase Firestore as it's primary database.
- Healthify has full offline support, it uses Android's ROOM database for caching all data offline.
- Healthify is made using Kotlin and following Modern Android Development practices.
- Healthify uses all Jetpack libraries and follows MVVM architecture. It also has a G.O.A.T rating in Android's  M.A.D scorecard.
- Healthify's code follows all the best practices and software development principles which make it a very good learning resource for beginners.
- Healthify's code is properly linted using Ktlint.

![summary.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629894600750/lYuPA7nYY.png)

### Tech Stack
 
 - Android 
 - Kotlin
 - Android Jetpack Components
 - Android Architecture Components
 - Firebase
 - Auth0
  
#### **This is how I authenticate users using Auth0**


```kotlin
private fun loginUser() {
    viewModel.startLoading()
    WebAuthProvider
        .login(auth0)
        .withScheme(getString(R.string.scheme))
        .withScope("openid profile email read:current_user update:current_user_metadata")
        .start(
            requireContext(),
            object : Callback<Credentials, AuthenticationException> {
                override fun onFailure(error: AuthenticationException) {
                    viewModel.sendError(error.message.toString())
                }

                override fun onSuccess(result: Credentials) {
                    getUserProfile(result.accessToken)
                }
            }
        )
}

```

#### **This is how I am getting user profile data using auth0**

This is how I get user data from my fragment and send it to viewModel to get data from database

```kotlin
 private fun getUserProfile(accessToken: String) {
    val client = AuthenticationAPIClient(auth0)
    client.userInfo(accessToken)
        .start(object : Callback<UserProfile, AuthenticationException> {
            override fun onFailure(error: AuthenticationException) {
                viewModel.sendError(error.message.toString())
            }

            override fun onSuccess(result: UserProfile) {
                viewModel.saveUser(result)
                viewModel.loginComplete()
            }
        })
}

```

#### This is how I'm logging out users from my app.
```kotlin
private fun logoutUser() {
    WebAuthProvider
        .logout(auth0)
        .withScheme(getString(R.string.scheme))
        .start(
            requireContext(),
            object : Callback<Void?, AuthenticationException> {
                override fun onFailure(error: AuthenticationException) {
                    viewModel.logoutFailed()
                }

                override fun onSuccess(result: Void?) {
                    viewModel.logoutComplete()
                }
            }
        )
}
```

### Challenges I faced and how I solved them ✅

**Developing a software is full of challenges and twists and turns.**

- Making the notifications to remind user to drink after after every 1 hour of the last water intake was a difficult thing to implement, mainly handling case when user adds another water intake before the 1 hour interval. I figured it out by cancelling the old alarm when a new water intake is tracker and add new alarm for it. 🎉
  
- Making such complex UI in Android's XML design system is a very difficult thing and also handling light and dark theme together was also quite tough. I figured out a way to manage both UI's by maintaining two separate colors.xml to set the colors and same for styles.xml and drawable files. 🎉
  
- The Statistics screen was also quite a tricky part, mainly customizing the graphs according to my designs was a very difficult thing to do as the library had almost no documentation. After some hours of researching into its code I found out the exact properties to alter to make it look close to what I wanted it to. 🎉

### Future Improvements 🌟

- Adding more features to track like protein intake , calorie tracking and many more
- Having a smart watch version of this app will be the cherry on the cake.
- Making the app completely offline ready so users can add water/sleep while being offline and as soon as the phone is online, data will get synced with the remote database
- Improve the Statistics section a bit.
- Improving the XP ranking system.


### Source Code 👩‍💻

If you want to have a look at the source code of the app, here is the link to the Github Repository 
[Healthify](https://github.com/Vaibhav2002/Healthify) 

You can download the latest version of Healthify from https://github.com/Vaibhav2002/Healthify/releases/tag/v1.0.0

**Feel free to contribute to Healthify and raise issues if you find any.**


### Vote of thanks 👏

I would like to thank **Hashnode Discord server** for providing such a good support. Special thanks to the members of **Auth0** for helping me fix some issues that I faced while integrating auth0

---

## If you like my projects and want to support me to build more cool open source projects
  
<a href="https://www.buymeacoffee.com/VaibhavJaiswal"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=VaibhavJaiswal&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff"></a>

---
