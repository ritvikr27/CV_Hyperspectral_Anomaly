# CV_Hyperspectral_Anomaly
Hyperspectral Anomaly Detection using Reed Xiaoli Algorithm

_**the changes and addition of this information was done as there were a lot of queries raised regarding hyperspectral images, the RX algorithm & the Mahalanobis distance during the presentation, therefore, I'm adding content related to them also in the readme._

_**this project is going to be developed further using more robust and powerful ML & DL algorithms for increasing the accuracy of the model and to get a better understanding of the concepts, also coz this is fun to do, so I’ll develop it more over the course of next few months with the goal of possibly trying to also use DL & NNs._

Hyperspectral imaging is a sophisticated imaging technique that captures a wide spectrum of light for each point in an image, extending beyond the primary colors of red, green, and blue that our eyes or conventional cameras can see. This technique divides the spectrum into many more bands, allowing it to capture the electromagnetic spectrum from the visible light to near-infrared, and sometimes even mid-infrared or thermal infrared. Each band represents a specific wavelength range, providing detailed spectral for each pixel in the image.

Importance of hyperspectral images: hyperspectral images are incredibly valuable across various fields due to their ability to identify, analyze, and differentiate objects and materials based on their specteal signature. This capability is crucial for applications such as: 
1.	Environmental Monitoring: Hyperspectral imaging can detect pollutants in water, monitor vegetation health, and assess biodiversity, contributing significantly to conservation efforts.
2.	Agriculture: It helps in precision farming by analyzing crop health, soil conditions, and moisture levels, enabling farmers to maximize yields while conserving resources.
3.	Mineralogy: Identifying minerals and their compositions in geological surveys is streamlined, aiding in exploration activities.
4.	Defense and Surveillance: The technology assists in camouflage detection, target identification, and surveillance by distinguishing objects based on their spectral characteristics.
5.	Medical Imaging: Hyperspectral imaging aids in diagnosing diseases and conditions by detecting variations in tissue composition and blood oxygenation levels.

Generating hyperspectral images: these images are generated using specialized cameras that capture light across a broad range of wavelength. These cameras are equipped with a dispersive element (like a prism or similar components) which separates the incoming light into its spectral components. The camera’s sensor then records these components, producing a three-dimensional dataset known as a hyperspectral cube. This cube has two spatial dimensions (height and width of the scene) and one spectral dimension (wavelengths), offering detailed spectral information for every pixel.


Why Hyperspectral imaging is necessary?
For detecting and classifying materials based on their spectral signatures which is not possible with traditional imaging methods. This capability is vital for:
1. Detailed Analysis and Detection: The detailed spectral information allows for the precise identification of materials and objects, even in complex scenes. 2. Non-Destructive Testing: It enables the analysis of subjects without altering or damaging them, crucial for historical document analysis, art restoration, and medical diagnostics. 3. Enhanced Decision Making: The rich information provided supports better decision-making in agriculture, environmental management, and other critical areas, contributing to more sustainable practices. 
In summary, hyperspectral imaging is a powerful tool that offers detailed insights into the material composition of objects and phenomena, significantly benefiting scientific research, industrial applications, anomaly detection, and environmental conservation.


This project advances the field of hyperspectral anomaly detection by applying the Reed Xiaoli (RX) algorithm to hyperspectral image data, which comprises two primary components: the map and the data. The map component indicates anomalies—objects or pixel values that are not expected to be present in the scene—while the data component represents the actual image. By applying the RX algorithm to the image data, we generate anomaly scores for every pixel, quantifying how much each pixel deviates from its surroundings.

The main objective is to utilize various thresholding techniques to isolate anomalies in the hyperspectral image data effectively. The goal is to produce an output that closely matches or approximates the anomaly map provided with the image data. This involves experimenting with different thresholding methods to determine the most effective technique for identifying anomalies, as highlighted by the map component.



IMPLEMENTATION:
The approach involves several steps, starting with the application of the RX algorithm to compute anomaly scores for each pixel. Subsequently, we explore four distinct thresholding techniques to refine anomaly detection:  Fixed Thresholding: We begin with a straightforward method, setting a manual threshold value of 0.5. This technique serves as a baseline for comparison against more dynamic methods.  Mean Thresholding: This technique involves calculating the mean anomaly score across all pixels and using this average value as the threshold. It adjusts dynamically to the overall anomaly score distribution of the image.  Mean and Standard Deviation Thresholding: Building on the mean thresholding approach, this method also considers the standard deviation of anomaly scores. It aims to capture a broader range of anomalies by accounting for the variance in scores.  Percentile Thresholding: We apply percentile-based thresholding at 99%, 95%, and 90% levels. This method selects thresholds based on the distribution of anomaly scores, aiming to isolate the most significant anomalies by focusing on the upper echelons of the score distribution.


In the implementation, the Reed Xiaoli (RX) algorithm was applied in two distinct manners to calculate anomaly scores:
1.	Normalized Anomaly Scores: Initially, the RX algorithm was applied to produce normalized anomaly scores. This approach ensures that the scores are scaled to a common range, facilitating a consistent basis for comparison across different parts of the image.
2.	Raw Anomaly Scores: Subsequently, the algorithm was applied without normalizing the anomaly scores. This allowed us to assess the impact of raw score magnitudes on the effectiveness of each thresholding technique.



The Reed Xiaoli (RX) Algorithm:
 The Reed Xiaoli (RX) algorithm, also known as the RX detector, is a widely used technique for anomaly detection in hyperspectral imaging data. Developed by Irving Reed and Xiaoli Yu, the RX algorithm is specifically designed to identify anomalies within a dataset without prior knowledge of the background or the anomalies themselves. It operates on the principle of detecting pixels that significantly differ from most of the background in terms of spectral characteristics.

How the RX algorithm works?
The RX algorithm utilizes the statistical property of the Mahalanobis distance to measure the spectral discrepancy of each pixel from the background. The Mahalanobis distance is a multidimensional measure that considers the correlations of the dataset's variables and scales the distances between points accordingly. 
In the context of hyperspectral images, this distance is calculated for each pixel relative to the distribution of the background pixels, effectively identifying pixels whose spectral signatures deviate from the norm. The algorithm processes the hyperspectral data cube, which consists of spatial and spectral information, to calculate this distance for every pixel. A high Mahalanobis distance indicates that the pixel's spectral signature is significantly different from the background, flagging it as an anomaly.

Importance of RX Algorithm in Anomaly Detection:
1.	Sensitivity to Subtle Anomalies: A key strength of the RX algorithm is its sensitivity to subtle anomalies. It can detect minor spectral deviations, making it highly effective for applications requiring precision, such as mineral exploration, environmental monitoring, and military surveillance.
2.	No Requirement for Prior Information: The RX algorithm does not require prior knowledge of the anomalies' characteristics or the background. This makes it highly versatile and applicable in various fields where such information is unknown or difficult to obtain.
3.	Wide Applicability: Given ability to operate on complex hyperspectral data, the RX algorithm is suitable for a broad range of applications. It is used in agriculture for crop health monitoring, in environmental science for pollution detection, and in security for identifying objects or materials that are out of place.
4.	Facilitation of Further Analysis: By identifying anomalies, the RX algorithm enables further analysis of these anomalies for material identification, change detection, or trend analysis. This is crucial for research and operational applications where identifying the unknown is the first step toward understanding a phenomenon or solving a problem.
To summarize, the RX algorithm is a cornerstone for anomaly detection in hyperspectral images, offering a powerful tool for identifying spectral anomalies across various domains. The importance lies in its robustness, versatility, and the role it has in enabling detailed analysis of materials and phenomena based on their respective spectral signatures.


Mahalanobis Distance:
The Mahalanobis distance is a measure of distance in multidimensional space that accounts for the variance in each dimension and the covariance between dimensions. 
Unlike Euclidean distance, which measures the straight-line distance between two points, the Mahalanobis distance considers the correlations of the data set and is scale-invariant. This means it measures how many standard deviations a point is from the mean of a distribution, making it particularly useful for identifying outliers in data with multiple variables.

![image](https://github.com/ritvikr27/CV_Hyperspectral_Anomaly/assets/76433779/e790fe84-ab5f-476e-aeab-793b14cff8d2)

Importance of Mahalanobis distance for the RX algorithm:
1.	Sensitivity to Spectral Variability: By considering the variance and covariance of the background spectral data, the Mahalanobis distance can accurately measure how much an observation deviates from the norm. This is crucial in hyperspectral imagery, where each pixel contains a spectrum with information across many wavelengths. 
2.	Adaptability to Multivariate Data: Hyperspectral data is multivariate, where each pixel represents information across potentially hundreds of spectral bands. The Mahalanobis distance's ability to handle multivariate data makes it particularly suited to analyzing hyperspectral images. 
3.	Anomaly Detection: In the context of the RX algorithm, the Mahalanobis distance quantifies the anomaly score of each pixel. A high score indicates that the pixel's spectral signature significantly deviates from the background distribution, thus flagging it as an anomaly. This is important for detecting materials, objects, or conditions that differ from the expected background. 
4.	Robustness to Correlated Data: Hyperspectral data bands are often correlated, which may affect the performance of distance metrics like the Euclidean distance. The Mahalanobis distance, by incorporating the covariance matrix, is not biased by these correlations which makes it more effective for detecting true anomalies.
Therefore, the Mahalanobis distance’s capability to account for the statistical properties of the data makes it crucial in the RX algorithm which enables robust and sensitive anomaly detection in complex hyperspectral datasets. This is essentially important in applications where the precise identification of anomalous features in a scene can help in making critical decisions in environmental monitoring, defense, and other domains.


Link for the dataset: http://xudongkang.weebly.com/data-sets.html

More information about this topic and other datasets: https://zephyrhours.github.io/sources.html


