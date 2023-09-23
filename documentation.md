## Technologies Used
- **Languages:** HTML, CSS, JavaScript, React JS
- **Other Tech:** NPM, VITE, RapidAPI, VScode

# Introduction to Files Created Using React Vite

1. **Package.json**: This file is a crucial configuration file used to manage project dependencies, scripts, and other metadata about the project.

2. **Package-lock.json**: The primary purpose of `package-lock.json` is to provide dependency version information for your project, ensuring that the exact same versions of dependencies are consistently installed in different environments.

3. **.gitignore**: A `.gitignore` file is a configuration file used in Git to specify which files and directories should be ignored by the version control system.

4. **Readme.md, Documentation.md**: These files contain basic and detailed documentation of the project.

5. **.env/.env.example**: The `.env` file, often referred to as an environment variable file, is a configuration file used to store environment-specific settings and configuration values for software applications. It's a plain text file typically named `.env` (short for "environment") and is used to define key-value pairs of variables that your application can access.

6. **Public Directory**: In React, the `public` directory is a special directory used for serving static assets and files that don't need to go through the build process. It's often used to store files like images, fonts, and HTML files that should be included in the final build of your React application as-is, without being transformed or bundled by tools like Webpack or Babel.

7. **src Directory**: This directory is where you typically place your source code and React components. Vite is a build tool that's designed to be fast and efficient, and it uses the `src` directory as the entry point for your project.


## Files and Folders in the `src` Directory

1. **index.js**: This is the main file responsible for rendering all of the components. It serves as the entry point of your React application.

2. **App.js**: The `App.js` file bundles up all of the components into one cohesive unit. It is then imported into `index.js`, where the application's rendering begins.

3. **index.css**: The `index.css` file is responsible for designing the layout of your application. It defines the styles and is also imported into `index.js` to apply those styles to your components.

## Folders in the `src` Directory

4. **components Folder**: The `components` folder contains all the individual components used in your application. These components are imported and bundled together in `App.js` to build the user interface.

5. **utils Folder**: The `utils` folder houses all the constants and utility functions used in your application. It provides a central location for managing constants and reusable code.


# 1. App.jsx

* import { BrowserRouter, Routes, Route } from "react-router-dom";
* import { Box } from '@mui/material';
* import { ChannelDetail, VideoDetail, SearchFeed, Navbar, Feed } from './components';

* BrowserRouter : 
* Box :
* Navbar :
* Routes :
* "<Route exact path='/' element={<Feed />} />" :
* Feed :
* VideoDetail :
* ChannelDetail :
* SearchFeed :

# 2. Navbar.jsx

* import { Stack } :
* import { Link } :
* import logo, SearchBar :
* "Link to="/"  :

## 2.1.  SearchBar.jsx
* import { useNavigate } { Paper, IconButton } { Paper, IconButton } SearchIcon :
* const [searchTerm, setSearchTerm] = useState('') :
* const navigate = useNavigate() :
* const onhandleSubmit = (e) => {e.preventDefault() :
*  "if (searchTerm){navigate(`/search/${searchTerm}`);setSearchTerm('');}}" :
*  Paper component='form' nSubmit={onhandleSubmit} :
*  input value={searchTerm} onChange={(e) => setSearchTerm(e.target.value)} :

# 3. Feed
* import { Box, Stack, Typography } :
* import { fetchFromAPI } :
* import { Videos, Sidebar } :
* const [selectedCategory, setSelectedCategory] = useState("New"): 
* const [videos, setVideos] = useState(null):
* useEffect(() => {setVideos(null);
  fetchFromAPI(`search?part=snippet&q=${selectedCategory}`)
  .then((data) => setVideos(data.items))}, [selectedCategory]);
* Sidebar selectedCategory={selectedCategory} setSelectedCategory={setSelectedCategory}
* Videos videos={videos}

## 3.1 Sidebar.jsx
* import  { Stack }  { categories }
* const Categories = ({ selectedCategory, setSelectedCategory })
* {categories.map((category) => ()
* onClick={() => setSelectedCategory(category.name)}
* key={category.name}

## 3.2 Videos.jsx
* import { ChannelCard, Loader, VideoCard } from "./"
* const Videos = ({ videos, direction }) => {if(!videos?.length) return <Loader />
* {videos.map((item, idx) => (
* Box key={idx}
* {item.id.videoId && <VideoCard video={item} /> }
* {item.id.channelId && <ChannelCard channelDetail={item} />}

## Loader.jsx
* import { Box, CircularProgress, Stack }
* CircularProgress

## VideoCard.jsx
* import { Link } { Typography, Card, CardContent, CardMedia }, CheckCircleIcon
* import { demoThumbnailUrl, demoVideoUrl, demoVideoTitle, demoChannelUrl, demoChannelTitle } from "../utils/constants";
* Card
* Link to={videoId ? `/video/${videoId}` : `/video/cV2gBU6hKfY` }
* CardMedia image={snippet?.thumbnails?.high?.url || demoThumbnailUrl} alt={snippet?.title}
* CardContent
* Link to={videoId ? `/video/${videoId}` : demoVideoUrl }
* Typography {snippet?.title.slice(0, 60) || demoVideoTitle.slice(0, 60)} :
* Link to={snippet?.channelId ? `/channel/${snippet?.channelId}` : demoChannelUrl}
* Typography {snippet?.channelTitle || demoChannelTitle}

## ChannelCard.jsx
* import {CardContent, CardMedia, CheckCircleIcon}
* import { demoProfilePicture } from '../utils/constants';
* const ChannelCard = ({ channelDetail, marginTop }) => ()
* Link to={`/channel/${channelDetail?.id?.channelId}`}
* CardContent
* CardMedia
* image={channelDetail?.snippet?.thumbnails?.high?.url || demoProfilePicture}
* alt={channelDetail?.snippet?.title}
* Typography{channelDetail?.snippet?.title}{' '}
* CheckCircleIcon
* {channelDetail?.statistics?.subscriberCount && (<Typography>
* {parseInt(channelDetail?.statistics?.subscriberCount).toLocaleString('en-US')} Subscribers
          






