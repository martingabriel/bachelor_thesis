# A Proposed Multiplatform Mobile Application fo Fast Communication Between Students and Teachers

## What you find here

This is collection of files used to write my bachelor thesis on Tomas Bata University in Zlin. Thesis is written in czech language.

## Project architecture

Solution is based on Microsoft technologies like .NET Core, Azure, Xamarin, and many others.

Core features:

1. **.NET Core server app**
   - User autentification
   - Get data from STAG UTB server
   - API for Xamarin app
   - Send push-notifications

2. **Xamarin multiplatform App**
   - View data from .NET Core server API
   - Send messages to multiple users (server API)
   - Receive messages as push-notifications

## STAG API services

STAG API services that have been used in this project:

1. **getRozvrhovaAkceInfo** 

2. **getRozvrhoveAkce**

3. **getUciteleRoakce**

4. **getRozvrhByStudent**

5. **getRozvrhByUcitel**