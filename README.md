# COVID-19 Detection using CXR Images

Confronting the pandemic of COVID-19 is nowadays one of the most prominent challenges of the human species. A key factor in slowing down the virus propagation is the rapid diagnosis and isolation of infected patients. The general method for COVID-19 identification, the Reverse transcription-polymerase chain reaction method, is time-consuming and due to the pandemic is in short supply. Thus, researchers have been looking for alternative screening methods and deep learning applied to chest X-rays of patients has been showing promising results. Despite their success, the computational cost of these methods remains high, which imposes difficulties on their accessibility and availability. Thus, the main goal of this work is to propose an accurate yet efficient method in terms of memory and processing time for the problem of COVID-19 screening in chest X-rays. The proposed work attempts to apply a neural-network-based detection of SARS COVID-19 on radiographs which is implemented using Python 3.6. Detection and diagnosis tools offer a valuable second opinion to the doctors and assist them in the screening process. Two identical models (VGG16 classifier) were implemented with two different optimizer algorithms namely Adam optimizer and RMSprop optimizer. A custom dataset was created by collecting, excluding, selecting and relabeling data from various CXR image datasets from reliable sources on the Internet. Each of the models were trained with different dataset segmentation and a different number of epochs. Finally, output metrics were collected and the results were tabulated and inference was drawn based on that regarding the use of each model in particular cases or scenarios which could be considerable.
<br>

### About this repo

This repository contains the dataset and the Python program corresponding to the created models. The dataset has been custom made and the images have been sourced from many different research institutes' websites. The dataset has been divided into two classes - 'covid' containing 601 covid-positive patients' CXR images, and 'normal' containing 1608 normal CXR images. In order to load the dataset, replace ```dataset path``` by the actual path where you have stored the dataset.
There are two Python (.py) files corresponding to two models. Model-1 refers to the one using the Adam Optimizer, and Model-2 refers to the one using the RMSProp optimizer. For extended use, the models can be saved to disk by appending ```model.save(args["model"], save_format="h5")``` at the end of the source code.<b> Note : This would take extra disk space. </b>
The repo also contains sample images for the accuracy and plots, and also the confusion matrix obtained.
<br>

### Results Obtained
Initially the model was trained with a batch of 25 images from both classes (i.e., 25+25 = 50 images) for a total of 75 epochs. Then the model was tested for increasing number of images (200+200, 600+600, 600+1000), with both optimizers. So, after training has completed, first of all predictions are made on the testing set, and the predication indices are obtained. The model was trained and the below table shows the different performance metrics obtained for the different data segments and number of epochs for each of the models. The model using Adam as optimizer took a little more than 4 hours to be trained, while the model using RMSProp optimizer took just under an hour to give the results. Also, it was observed that Adam optimizer gave better accuracy for larger data segments than RMSProp. On the other hand, RMSProp showed higher model losses than Adam.

<p align = 'center'>
<table class=MsoTableGrid border=1 cellspacing=0 cellpadding=0 width="94%"
 style='width:94.68%;margin-left:22.25pt;border-collapse:collapse;border:none;
 mso-border-alt:solid windowtext .5pt;mso-yfti-tbllook:1056;mso-padding-alt:
 0in 5.4pt 0in 5.4pt'>
 <tr style='mso-yfti-irow:0;mso-yfti-firstrow:yes;height:31.85pt'>
  <td width="12%" rowspan=2 valign=top style='width:12.94%;border:solid windowtext 1.0pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:31.85pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Model<o:p></o:p></span></p>
  </td>
  <td width="9%" rowspan=2 valign=top style='width:9.22%;border:solid windowtext 1.0pt;
  border-left:none;mso-border-left-alt:solid windowtext .5pt;mso-border-alt:
  solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:31.85pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Epochs<o:p></o:p></span></p>
  </td>
  <td width="11%" rowspan=2 valign=top style='width:11.84%;border:solid windowtext 1.0pt;
  border-left:none;mso-border-left-alt:solid windowtext .5pt;mso-border-alt:
  solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:31.85pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Dataset segments<o:p></o:p></span></p>
  </td>
  <td width="65%" colspan=6 valign=top style='width:65.98%;border:solid windowtext 1.0pt;
  border-left:none;mso-border-left-alt:solid windowtext .5pt;mso-border-alt:
  solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:31.85pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Performance Metrics<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:1;height:27.65pt'>
  <td width="11%" valign=top style='width:11.66%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Accuracy<o:p></o:p></span></p>
  </td>
  <td width="12%" valign=top style='width:12.7%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Sensitivity<o:p></o:p></span></p>
  </td>
  <td width="12%" valign=top style='width:12.74%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Specificity<o:p></o:p></span></p>
  </td>
  <td width="10%" valign=top style='width:10.42%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Support<o:p></o:p></span></p>
  </td>
  <td width="7%" valign=top style='width:7.32%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>F1-score<o:p></o:p></span></p>
  </td>
  <td width="11%" valign=top style='width:11.12%;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:27.65pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Precision<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:2;height:23.95pt'>
  <td width="12%" rowspan=5 valign=top style='width:12.94%;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Model-1 (Adam)<o:p></o:p></span></p>
  </td>
  <td width="9%" rowspan=4 style='width:9.22%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>75<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>25+25<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>75%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>80%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>70%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>10,10<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.76<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.73<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:3;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>200+200<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.75%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.33%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.17%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>80,
  81<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:4;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>600+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.81%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.65%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.01%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>240,
  240<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:5;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>1000+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.87%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.76%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.91%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>241,643<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.98<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.97<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:6;height:23.95pt'>
  <td width="9%" style='width:9.22%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>150<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>1000+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.53%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.17%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.29%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>241,643<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.97<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.96<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:7;height:23.95pt'>
  <td width="12%" rowspan=5 valign=top style='width:12.94%;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none'><span
  style='font-size:10.0pt;font-family:"Times New Roman",serif;mso-bidi-font-weight:
  bold'>Model-2 (RMSprop)<o:p></o:p></span></p>
  </td>
  <td width="9%" rowspan=4 style='width:9.22%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>75<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>25+25<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>92.75%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>95.50%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>96.445<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>10,
  10<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.92<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.93<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:8;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>200+200<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.38%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>100%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.77%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>80,
  81<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.98<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:9;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>600+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.17%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.32%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.17%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>240,
  240<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:10;height:23.95pt'>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>1000+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>98.64%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>95.85%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.69%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>241,
  643<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.97<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.99<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:11;mso-yfti-lastrow:yes;height:23.95pt'>
  <td width="9%" style='width:9.22%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>150<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.84%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>1000+600<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.66%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>97.99%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.7%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>96.01%<o:p></o:p></span></p>
  </td>
  <td width="12%" style='width:12.74%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>99.55%<o:p></o:p></span></p>
  </td>
  <td width="10%" style='width:10.42%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>241,
  643<o:p></o:p></span></p>
  </td>
  <td width="7%" style='width:7.32%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.98<o:p></o:p></span></p>
  </td>
  <td width="11%" style='width:11.12%;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:23.95pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>0.98<o:p></o:p></span></p>
  </td>
 </tr>
</table></p>

#### Comparison between the two models
<p align = 'center'>
<table class=MsoTable15Grid1Light border=1 cellspacing=0 cellpadding=0
 width=436 style='width:327.05pt;margin-left:102.35pt;border-collapse:collapse;
 border:none;mso-border-alt:solid windowtext .5pt;mso-yfti-tbllook:1056;
 mso-padding-alt:0in 5.4pt 0in 5.4pt;mso-border-insideh:.5pt solid windowtext;
 mso-border-insidev:.5pt solid windowtext'>
 <tr style='mso-yfti-irow:-1;mso-yfti-firstrow:yes;mso-yfti-lastfirstrow:yes;
  height:12.25pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:12.25pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none;mso-yfti-cnfc:
  1'><span style='font-size:10.0pt;font-family:"Times New Roman",serif;
  mso-bidi-font-weight:bold'>Model-1<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border:solid windowtext 1.0pt;
  border-left:none;mso-border-left-alt:solid windowtext .5pt;mso-border-alt:
  solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:12.25pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:normal;mso-layout-grid-align:none;text-autospace:none;mso-yfti-cnfc:
  1'><span style='font-size:10.0pt;font-family:"Times New Roman",serif;
  mso-bidi-font-weight:bold'>Model-2<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:0;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>Better
  accuracy than Model-2<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>Slightly
  lower accuracy than Model-1<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:1;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  sensitivity, specificity<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  sensitivity, specificity<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:2;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>Stable
  model<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>Stable
  model<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:3;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  F1-score<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  F1-score<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:4;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  precision<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  precision<o:p></o:p></span></p>
  </td>
 </tr>
 <tr style='mso-yfti-irow:5;mso-yfti-lastrow:yes;height:20.85pt'>
  <td width=219 valign=top style='width:164.1pt;border:solid windowtext 1.0pt;
  border-top:none;mso-border-top-alt:solid windowtext .5pt;mso-border-alt:solid windowtext .5pt;
  padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>High
  training time (or high computational cost)<o:p></o:p></span></p>
  </td>
  <td width=217 valign=top style='width:162.95pt;border-top:none;border-left:
  none;border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  mso-border-top-alt:solid windowtext .5pt;mso-border-left-alt:solid windowtext .5pt;
  mso-border-alt:solid windowtext .5pt;padding:0in 5.4pt 0in 5.4pt;height:20.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:normal;mso-layout-grid-align:
  none;text-autospace:none'><span style='font-size:10.0pt;font-family:"Times New Roman",serif'>Low
  training time (or low computational cost)<o:p></o:p></span></p>
  </td>
 </tr>
</table></p>

### Conclusion
Model-1 (Adam optimizer) had slightly better accuracy than Model-2 (RMSprop optimizer) over the comparably larger dataset segmentations, as expected. In medical diagnosis, test sensitivity is the ability of a test to correctly identify those with the disease (true positive rate), whereas test specificity is the ability of the test to correctly identify those without the disease (true negative rate).Sensitivity and specificity of both the models remained on the higher sides, thus inferring a proper implementation of the model serving proper detection criteria. The appropriate stability of the models can be conjected by the support values provided by the models. The F1 score is the harmonic mean of the precision and recall. The highest possible value of an F-score is 1, indicating perfect precision and recall, and the lowest possible value is 0, if either the precision or the recall is zero. The F1-scores of the cases implemented for each model yielded 0.9+ value except the (25+25) segment, 75epochs case for Model-1(Adam optimizer) which is due to the very small dataset segment for applying Adam optimizer. Higher F1-score implies high accuracy and high recall. The precision was also high for almost all the cases, the modal value for the collection of precision across the different cases being 0.99(unimodal with 5 out of 10 occurrences).
Hence, summing up, Model-1 showed slightly better performance metrics but took more time to train each case with training time increasing with increase in dataset segmentation and increase in number of epochs. Model-2 displayed a slight downside on the performance metrics but took drastically less time to train as compared to Model-1. As for application of the proposed work it can be concluded that the Model-1 can be used for more accurate but time consuming detections, hence meant for clinical laboratory tests for COVID-19 detection. It has high computational cost and is time prohibitive. On the other hand the Model-2 has slightly lower accuracy but takes a fraction of the computation cost as of Model-1. Hence it can be used for faster and slightly less accurate detections needed for portable applications as in devices; since for that aim the models must have a low footprint and low latency, that is, the models must require little memory and perform inference quickly to allow use on embedded devices and large scale, enabling integration with smartphones and medical equipment.

