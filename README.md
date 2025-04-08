# Zoom Video SDK UI Toolkit React sample

Use of this sample app is subject to our [Terms of Use](https://explore.zoom.us/en/video-sdk-terms/).

This repo is a [React](https://reactjs.org/) app generated via [Vite](https://vitejs.dev/) that uses the [Zoom Video SDK UI toolkit](https://developers.zoom.us/docs/video-sdk/web/) to start and joins sessions.

![Zoom Video SDK](https://github.com/zoom/videosdk-ui-toolkit-web/raw/main/uitoolkitgalleryview.png)

## Installation

To get started, clone the repo:

`$ git clone https://github.com/zoom/videosdk-ui-toolkit-react-sample.git`

## Setup

1. Once cloned, navigate to the `videosdk-ui-toolkit-react-sample` directory:

   `$ cd videosdk-ui-toolkit-react-sample`

1. Then install the dependencies:

   `$ npm install`

1. Open the `videosdk-ui-toolkit-react-sample` directory in your code editor.

1. Open the `src/App.js` file, and enter values for the variables:

   | Variable                   | Description |
   | -----------------------|-------------|
   | authEndpoint          | Required, your Video SDK auth endpoint that securely generates a Video SDK JWT. [Get a Video SDK auth endpoint here.](https://github.com/zoom/videosdk-auth-endpoint-sample) |
   | config | Your Video SDK [session details](https://developers.zoom.us/docs/video-sdk/web/ui-toolkit/#create-a-configuration-object) and [enabled features](https://developers.zoom.us/docs/video-sdk/web/ui-toolkit/#supported-features). The `videoSDKJWT` will be set from the response of your `authEndpoint`. |
   | role | Required, `0` to specify participant, `1` to specify host. |

   Example:

   ```js
   var authEndpoint = "http://localhost:4000";
   var config = {
      videoSDKJWT: "",
      sessionName: "SessionA",
      userName: "UserA",
      sessionPasscode: "abc123",
      featuresOptions: {
         virtualBackground: {
            enable: true,
            virtualBackgrounds: [
            {
               url: "https://images.unsplash.com/photo-1715490187538-30a365fa05bd?q=80&w=1945&auto=format&fit=crop",
            },
            ],
         },
      }
   };
   var role = 1;
   ```

1. Save `App.js`.

1. Run the app:

   `$ npm run dev`

## Usage

1. Navigate to http://localhost:5173 and click "Join Session".

## Deployment

The React Sample App can be easily deployed to [GitHub Pages](#github-pages), or [another static web hosting service](#other-static-web-hosting), like an AWS S3 bucket.

### GitHub Pages

1. Clone this repo and configure the `authEndpoint`.

1. Create a new repo on [GitHub](https://github.com).

1. Add the remote to your project:

   `$ git remote add myorigin GITHUB_URL/GITHUB_USERNAME/GITHUB_REPO_NAME.git`

1. Open the `vite.config.ts` file and add `base: "/GITHUB_REPO_NAME/"` in the `defineConfig` helper.

1. Build your project:

   `$ npm run build`

1. Rename the `build` folder to `docs`

1. Git add, commit, and push your project:

   `$ git add -A`

   `$ git commit -m "deploying to github"`

   `$ git push myorigin main`

1. On GitHub, in your repo, navigate to the "settings" page, scroll down to the "GitHub Pages" section, and choose the "main" branch and "/docs" folder for the source.

1. Now your project will be deployed to https://GITHUB_USERNAME.github.io/GITHUB_REPO_NAME.

### Other Static Web Hosting

1. Build your project:

   `$ npm run build`

1. Deploy the complied `/build` directory to a static web hosting service, like an AWS S3 bucket.

### Advanced Deployment

For more advanced instructions on deployment, [see the React Deployment docs](https://create-react-app.dev/docs/deployment/).

## Need help?

If you're looking for help, try [Developer Support](https://devsupport.zoom.us) or our [Developer Forum](https://devforum.zoom.us). Priority support is also available with [Premier Developer Support](https://explore.zoom.us/docs/en-us/developer-support-plans.html) plans.
