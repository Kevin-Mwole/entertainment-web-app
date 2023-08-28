# Frontend Mentor - Entertainment web app solution

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Navigate between Home, Movies, TV Series, and Bookmarked Shows pages
- Add/Remove bookmarks from all movies and TV series
- Search for relevant shows on all pages
- **Bonus**: Build this project as a full-stack application
- **Bonus**: If you're building a full-stack app, we provide authentication screen (sign-up/login) designs if you'd like to create an auth flow

### Screenshot

![](https://user-images.githubusercontent.com/48052439/161436734-f6b27e17-506c-434a-9f09-a2ca73b6537f.png)



## My process

### Built with

- [Remix](https://remix.run/)
- Vanilla CSS
- Postgres
- [Prisma](https://prisma.io/)
- Cookie based authentication
- [Supabase](https://supabase.com/)
- [Docker](https://docker.com/)

### What I learned

This was my first time trying out Remix on a project. I really enjoyed the focus on web fundamentals, and server-side data loading. The Remix architecture means that except for the bookmarking functionality, the entire app will work with javascript disabled (or before javascript has loaded).

I also used this project to focus on working with an image-heavy site. Most of my work is normally with data-intensive applications, so images were not something I had explored in depth. I created responsive images that would serve appropriate files for the user's device. This was complicated by the images having different aspect ratios. I wanted to create a solution that would minimize layout shift but still allow the different aspect ratios. I achieved this with a combination of CSS Grid, CSS custom properties and `object-fit:cover`. The code was a bit more convoluted than I'd like. It's definitely a technique I'd like to refine.

I used plain cookie-based authentication for the first time too. Previously I'd always used a provider like OAuth but a simple username and password based approach was very straightforward to build.

### Continued development

This was the fist time I've used vanilla CSS on a large project for a while. I splilt up the CSS by component, but I think that was not the best idea. It was good to co-locate the styles, but results in a lot of network requests to get many small individual CSS files. I plan on experimenting with integrating SASS and remix to try and mitigate some of these problems.

Remix is super fast to load a site, as everything works before the javascript has loaded and the site is hydrated. But when there's data requirements, that data fetching can take time. This impacts the lighthouse scores for the site. The benefits of Remix's data-loading architecture seems like they will only work with colocated servers and data. I used Supabase with Vercel, and so there's a fair bit of network latency making the database queries. One option would be to try out using [Fly.io](https://fly.io) for hosting, as they provide long running servers, not just serverless, and their own postgres databases.

