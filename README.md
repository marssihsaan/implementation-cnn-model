## Implementation of CNN Model for Detecting Online Gambling Ads on the Homepage via Crawling System

This project involves the integration of a Convolutional Neural Network (CNN) model into the homepage of a website to detect spam online gambling advertisements. The system works by automatically crawling and analyzing images present on the website. The primary objective is to identify and classify whether an image contains elements related to online gambling advertisements or not.

## Key Features:

1. Automated Image Crawling: The system uses a web crawler to extract images from the homepage dynamically. This allows for continuous monitoring of the website, ensuring that all images are checked for potential spam ads in real-time.

2. CNN-based Image Classification: The CNN model, trained on a dataset of online gambling ads and non-gambling images, is applied to classify the crawled images. It effectively distinguishes between legitimate images and those containing promotional content for online gambling.

3. Real-time Detection: As the model is integrated into the homepage, it provides real-time detection of online gambling ads, enabling immediate action to block or report such content.

4. Accuracy and Scalability: The use of CNN provides a robust solution with high accuracy for image classification tasks. This ensures minimal false positives and negatives, allowing the system to scale and be used on larger platforms without compromising performance.

## Code Explanation

### Libraries

- **`tensorflow.keras.models.load_model`**: Loads the pre-trained deep learning model.
- **`requests`**: Handles HTTP requests to retrieve web content, such as images.
- **`PIL.Image`**: Processes images downloaded from the web.
- **`BytesIO`**: Converts raw HTTP responses into a readable image format.
- **`numpy`**: Used for numerical operations on arrays (image data).
- **`tensorflow`**: Provides tools to resize, normalize, and predict images using the loaded model.
- **`IPython.display.Image` and `display`**: Displays the images in Jupyter notebooks.
- **`BeautifulSoup`**: Extracts image URLs from HTML content.
- **`urllib.parse.urljoin` and `urlparse`**: Ensures image URLs are valid and absolute.

### Function `load_image_from_url`
This function downloads and processes an image from a URL. The image is converted to RGB format to ensure consistent preprocessing.

### Function `extract_image_urls`
This function extracts all image URLs from a given web page using `BeautifulSoup`. It converts relative image URLs to absolute ones to ensure they are valid for download.

### Function `display_and_predict_images`
- **Input**: A list of image URLs extracted from the webpage and the pre-trained TensorFlow model.
- **Process**: Downloads each image, resizes it to 256x256 pixels, normalizes it, and passes it through the model for prediction. The model predicts whether the image is classified as "Gambling" or "Non-Gambling."
- **Output**: Displays the images along with their predicted class labels. The results are sorted to show "Gambling" images first.

### Web Page URL
The URL of the web page from which the images will be scraped is defined in the `website_url` variable.

### TensorFlow Model
The pre-trained deep learning model is stored in the `models/modelbaru8.h5` file and is loaded to make predictions on the images.

### Final Process
The system scrapes all images from the web page, displays them, and shows the predicted class label for each image, with "Gambling" images shown first.

## How to Use
1. Make sure you have a pre-trained TensorFlow model (.h5 file) saved in the `models/` folder.
2. Prepare the link/URL of the website to be detected (you can use all url/link if qualify).
3. Run the script to scrape images from the specified website.
4. View the images along with their predicted classification.

## URL link
https://marssihsaan.github.io/webtesting/

![CNN Model Screenshot](https://github.com/marssihsaan/implementation-cnn-model/blob/main/Screenshot%202024-06-10%20142915.png)

## Results

![CNN Model Screenshot](https://github.com/marssihsaan/implementation-cnn-model/blob/main/Screenshot%202024-06-10%20145129.png)
![CNN Model Screenshot](https://github.com/marssihsaan/implementation-cnn-model/blob/main/Screenshot%202024-06-10%20145518.png)
![CNN Model Screenshot](https://github.com/marssihsaan/implementation-cnn-model/blob/main/Screenshot%202024-06-10%20145832.png)

## Deployment

https://github.com/marssihsaan/deployment-flask-modelcnnjudol

## Conclusion

This system and model work very effectively for detecting or classifying spam images of online gambling advertisements on a website homepage using a crawling system. Based on the detection results, out of the 2 spam images present, the system was able to detect all of them on the website, although there was 1 error where a non-gambling image was classified as gambling. This is quite reasonable, considering the accuracy achieved during training was 88%.
