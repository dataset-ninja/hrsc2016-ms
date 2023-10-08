**HRSC2016-MS: A Multi-Scale Updating Version of High Resolution Ship Collections 2016 (HRSC2016)** was developed by expanding and re-annotating the HRSC2016 dataset. Additionally, a novel multi-scale ship-detection framework (MSSDet) is proposed. 

HRSC2016 is the only open-source optical remote-sensing ship dataset. Owing to the difficulty of data acquisition and annotation, this dataset only contains 1070 images with 2976 ship instances. Moreover, most of the objects in the HRSC2016 dataset are larger than those in natural images. As is well known, the detection of small and size-varied objects is a challenging problem. Therefore, authors built an open-source ship detection benchmark with rich multi-scale ship targets named HRSC2016-MS.

The optical remote-sensing images in HRSC2016-MS come from two sources: previous studies on HRSC2016 and new collections from Google Earth. The first part of HRSC2016-MS is composed of the original data in HRSC2016, which is captured from the harbors in the United States. The original HRSC2016 dataset only contains 1070 optical remote-sensing images with 2976 ship instances, and a large number of small-ship instances are missing annotations, which motivated us to re-annotate the original data. The second part of HRSC2016-MS consists of 610 optical remote-sensing images collected from Google Earth captured from Murmansk harbor, Russia. Several examples of new collections are shown in Figure 1. The new collections include sea and sea–land images, day and night scenarios, clear and cloudy weather, and multi-scale ship instances. A comparison of the proposed HRSC2016-MS dataset and original HRSC2016 dataset is shown in Table 2. It can be seen that the proposed dataset contains a larger number of images and a wider range of image sizes than the original dataset. More importantly, the proposed dataset includes more multi-scale ship instances with a broader range of aspect ratios than the original dataset. Therefore, the diversity of the HRSC2016-MS dataset is increased compared with the original dataset, and the ship-detection task for this dataset is more challenging.

<!DOCTYPE html>
<html>
<head>
<style>
  table {
    border-collapse: collapse;
    width: 80%;
    margin: 20px auto;
  }

  th, td {
    border: 1px solid #dddddd;
    text-align: center;
    padding: 8px;
  }

  th {
    background-color: #f2f2f2;
  }
</style>
</head>
<body>

<table>
  <tr>
    <th>Dataset</th>
    <th>HRSC2016 [28]</th>
    <th>HRSC2016-MS</th>
  </tr>
  <tr>
    <td>Images</td>
    <td>1070</td>
    <td>1680</td>
  </tr>
  <tr>
    <td>Image sizes</td>
    <td>481 × 411∼1238 × 837</td>
    <td>361 × 339∼1329 × 830</td>
  </tr>
  <tr>
    <td>Instances</td>
    <td>2976</td>
    <td>7655</td>
  </tr>
  <tr>
    <td>Instance sizes</td>
    <td>48 × 22∼713 × 505</td>
    <td>5 × 10∼489 × 739</td>
  </tr>
  <tr>
    <td>Instance aspect ratios</td>
    <td>0.102∼10.0</td>
    <td>0.092∼11.692</td>
  </tr>
</table>

</body>
</html>

<span style="font-size: smaller; font-style: italic;">Comparison of proposed and original datasets.</span>

Authors visualized the original annotation files in the HRSC2016 dataset and found that numerous ship instances were mislabeled. The label set in the original dataset is a tree structure containing 1, 4, and 27 classes in ship-class, ship-category, and ship-type levels, respectively. Undoubtedly, an elaborate label set contributes to the convergence of the detector during the training period, but such a label set will create the problem of annotation omission because a limited label set cannot cover all types of ships. Therefore, in the proposed dataset, the label set only covers one class, i.e., ship. Authors used [roLabelImg](https://github.com/cgvict/roLabelImg) to label the images in the proposed dataset. Each ship instance is annotated in two ways, i.e., using a HBB and an OBB. 

Authors annotated the new images and re-annotated the original images with the proposed annotation method. Authors reduced the dimensions of the dataset to two based on principal component analysis (PCA) and then visualized the data distribution. As shown in Figure below, authors analyzed the data distribution of the original and proposed datasets and found that the two datasets have similar data distributions.

<img src="https://www.mdpi.com/remotesensing/remotesensing-14-05460/article_deploy/html/images/remotesensing-14-05460-g003.png" alt="image" width="800">

<span style="font-size: smaller; font-style: italic;">Data distribution of original HRSC2016 and proposed HRSC2016-MS datasets.</span>

Following the standard [COCO](https://scholar.google.com/scholar_lookup?title=Microsoft+COCO:+Common+Objects+in+Context&conference=Proceedings+of+the+European+Conference+on+Computer+Vision&author=Lin,+T.Y.&author=Maire,+M.&author=Belongie,+S.&author=Hays,+J.&author=Perona,+P.&author=Ramanan,+D.&author=Doll%C3%A1r,+P.&author=Zitnick,+C.L.&publication_year=2014&pages=740%E2%80%93755) evaluation approach, objects with sizes smaller than 32 × 32 pixels are small, objects with sizes larger than 96 × 96 pixels are large, and the rest are medium objects. The number of small, medium, and large objects in the original HRSC2016 dataset is 0, 319, and 2657, respectively, while it is 880, 2447, and 4328 in the proposed HRSC2016-MS dataset. Obviously, the proposed dataset contains more multi-scale ship instances, especially small objects.
