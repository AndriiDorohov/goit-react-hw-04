
# Homework

## Created Repository: `goit-react-hw-04`

- Repository: **goit-react-hw-04**  
- When submitting the homework, provide two links: one to the source files and one to the deployed page on **Vercel**.  
- The project was created using **Vite**.  
- During the task execution, there are no errors or warnings in the console.  
- For each component in the `src/components` folder, there is a separate folder containing the JSX file for the React component and the corresponding styles file. The folder name, component file (with the `.jsx` extension), and styles file (with `.module.css` before the extension) have the same name and match the names specified in the tasks (if provided).  
- **Default export** is used for components.  
- The **Axios** library is used for performing HTTP requests.  
- The JS code is clean and readable, using **Prettier**.  
- The styling is done using **CSS modules**.


---

## Image Search

[![Watch the demo](https://img.youtube.com/vi/tVLrzgdejQQ/0.jpg)](https://youtu.be/tVLrzgdejQQ)


### Image Search Service

In this task, you will use HTTP requests to fetch images from the [Unsplash](https://unsplash.com/developers) image service.

1. Register a developer account to get access to the documentation and API.
2. Create a new application record in your Unsplash dashboard (click on **New Application**). This step is required.
   - Choose a name for your app, e.g., **Image Gallery**, **Photo Search**, or something similar.
3. After creating the application, go to its page and get your **Access Key** under the **Keys** section to use for HTTP requests.

> ⚠️ For the free (Demo) version of applications, the number of HTTP requests is limited to **50 per hour**. Keep this in mind and avoid sending unnecessary requests.

### Helpful Documentation Sections

- [How to build a request URL](https://unsplash.com/documentation#schema)  
- [How to add the access key to requests](https://unsplash.com/documentation#public-authentication)  
- [How to search images by keyword](https://unsplash.com/documentation#search-photos)


### API Response

The backend responds with an object that contains all the necessary information.  
You will find:
- An **array of images**
- The **total number of pages** (for pagination)

Each image in the array is represented by an object with lots of metadata. The most important part for this task is the `urls` property, which contains links to different image sizes:

- Use the `small` version for **gallery cards**
- Use the `regular` version for the **modal window**

### Bonus

Don't limit yourself to just the required functionality!  
Use additional data from the image objects to display more interesting information in the modal window, such as:

- Author's name
- Number of likes
- Description
- And more

### Components

In this task, you need to independently identify the following components and add basic styling to the interface according to your taste. Use the demo video of the app as an example.

![Components structure](https://github.com/AndriiDorohov/goit-react-hw-04/raw/main/public/components.png)

### Header with Search Form

The `SearchBar` component receives one prop: `onSubmit` — a function to handle the input value when the form is submitted.  
It creates a DOM element with the following structure.

```jsx
<header>
  <form>
    <input
      type="text"
      autoComplete="off"
      autoFocus
      placeholder="Search images and photos"
    />
    <button type="submit">Search</button>
  </form>
</header>
```
If the text field is empty when the submit button is clicked, show the user a notification that they need to enter text to search for images.  
This validation is performed inside the `SearchBar` component at the moment of form submission.  
For notifications, use the [React Hot Toast](https://react-hot-toast.com/) library.

## Image Gallery

The `ImageGallery` component is a list of image cards that creates a DOM element with the following structure.
```jsx
<ul>
    {/* A set of list items with images */}
	<li>
		<div>
		  <img src="" alt="" />
		</div>
	</li>
</ul>
```

The gallery should render **only** when there are any loaded images.  
It is a good practice **not** to include the `<li>` element inside the card component but to keep it as part of the gallery component.

### Image Card

The `ImageCard` component is rendered inside the gallery element.  
It creates a DOM element with the following structure.

```jsx
<div>
  <img src="" alt="" />
</div>
```
## Loading Indicator

The `Loader` component is displayed below the gallery while images are loading.  
Use any ready-made component, for example [react-spinners](https://www.npmjs.com/package/react-spinners) or another.

While images are loading, the loading indicator should **not** replace the gallery, but simply render **below** it.  
This is critical when adding images to those already loaded.
## Error Message

The `ErrorMessage` component is rendered **instead** of the image gallery in case of an HTTP request error.  
A simple text message is sufficient.
## Load More Button

The `LoadMoreBtn` component renders a button with the text "Load more".  
When clicked, it should load the next batch of images and render them together with the previous ones.

The button should render **only** when there are some loaded images.  
If the images array is empty, the button should not render.

## Modal Window

The `ImageModal` component should be rendered inside the `App` component and receive all necessary data and functions via props from `App`.

When clicking on a gallery image, the `ImageModal` with a dark background should open, displaying the image in a large format.  
The modal should be configured to close when pressing the ESC key or clicking outside the modal.  
To implement the modal functionality, use the [React Modal](https://github.com/reactjs/react-modal?tab=readme-ov-file#examples) library.


