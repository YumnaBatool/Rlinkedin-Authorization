# Rlinkedin-Authorization
Procedure to authorize Rlinkedin package

1- install ROAuth, devtools

2- require(devtools)

3- install_github("mpiccirilli/Rlinkedin")

4- require(Rlinkedin)

5- require(ROAuth)

6- linkedin <- oauth_endpoint("requestToken", "authorize", "accessToken", base_url = "https://api.linkedin.com/uas/oauth/")

7- myapp <- oauth_app("linkedin", key = "your_api_key", secret = "your_api_secret")

8- token <- oauth1.0_token(linkedin, myapp,cache=FALSE)

9- sig <- sign_oauth1.0(myapp, token$oauth_token, token$oauth_token_secret)

To get Connections,

connections <- getMyConnections(token)

Getting Profiles of connections,

n <- n + 1

new <- array()

for(i in 1:3151){

  if( connections[i,1] != "private" ){

    profile <- getProfile(token,id=connections[i,1])

    new[n] <- profile[[1]][[j]]

    n = n +1

  }

}
