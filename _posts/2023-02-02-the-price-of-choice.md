---
date: 2023-02-02 12:00:00
layout: post
title: 'The Price of Choice'
subtitle: 'Maximizing profit in property sales'
description: >-
  ABC Company faces a dilemma in balancing their mission to provide property choices with maximizing profits through a 20% joint-profit sharing model. Selling large, high-priced properties poses a challenge, leaving the company torn between revenue and customer satisfaction.
image: >-
  https://drive.google.com/uc?export=view&id=1Ad2M3UB1Uoq-MhqXT4eiJJHVzng5coWa
optimized_image: >-
  https://drive.google.com/uc?export=view&id=1Ad2M3UB1Uoq-MhqXT4eiJJHVzng5coWa
category: data analysis
tags:
  - hypothesis testing
  - case study
  - eda
  - spreadsheet
  - revou
author: barklight
paginate: false
---
A data analyst should have the skills to perform comprehensive analysis, covering tasks such as data cleaning, exploratory data analysis (EDA), hypothesis testing, and regression analysis. These analyses lead to valuable insights and business recommendations. In the [RevoU course](http://rebrand.ly/damc-grad-rf?refcode=erladana), I had the opportunity to demonstrate these skills in a project, which further enhanced my proficiency in using spreadsheets as a data analyst.

> This project was completed as part of the assignment for the RevoU Full Stack Data Analytics course.

In this project, all the analyses were performed using [XLMiner Analysis ToolPak Add-on](https://workspace.google.com/marketplace/app/xlminer_analysis_toolpak/600284989882) in *Google Sheets*.

## Business understanding

### Background

The ABC Company, a property listing company in Malaysia, **aims to offer users and tenants a wide range of property options while maximizing their profits.** They adopt a 20% joint-profit sharing model, where properties with higher prices generate a greater percentage of revenue. **However, selling high-priced properties with numerous rooms or large sizes can be difficult.** <!-- challenging for this model's effectiveness. -->

### Dataset overview

The dataset contains 5,000 property listings in Malaysia. You can access the spreadsheet [here](https://docs.google.com/spreadsheets/d/e/2PACX-1vR6J-ElvUyQd5sLsoi1EKRK2KdleCDVZZKOYYKIRe4TTVVSjDMKERoJdb3kewQPoF9kHaqjVT2sO6aq/pubhtml), which includes the datasets, data dictionary, and analysis results.
The dataset includes various numerical variables, like `size`, `rooms`, `bathrooms`, and `car parks`, that provide insights through descriptive and inferential statistics. They help us understand the overall size of properties, which can be valuable information for properties that may be challenging to sell.
On the other hand, categorical variables such as `location`, `property type`, `property character`, and `furnishing` focus on gaining insights into demand based on location and characteristics. These insights can be particularly helpful in selling high-priced properties **because certain locations or property types, such as strategic areas or those with high land values, may make users and tenants willing to compromise on size or number of rooms.**

## Key ideas

To effectively analyze the data, there are a few key steps to follow:
1. Data cleaning
2. Exploratory data analysis
3. Statistical measurements
4. Recommendations

## Cleaning up the data

First, it's essential to clean up the data, ensuring its quality and removing any inconsistencies.
To be precise, I have performed the following tasks for cleaning up the data:

- Removed duplicates.
- Trimmed whitespace to remove redundant spaces.
- Uniformed HTML character codes (e.g., `22&#8217;x100&#8217`) to their proper values.
- Ensured the correct data type for each column.
- Imputed missing values in the size column using *simple linear regression*.
- Removed outliers using the *Interquartile Range* (IQR) method.

These actions resulted in the successful removal of **10.72%** of the data.

## Exploratory data analysis

Once the data was cleaned, I conducted descriptive statistics to get a clear picture. I specifically focused on the price and size columns. The `price` is important because **it directly affects the company's profit**, while `size` gives insights into property dimensions influenced by factors like the number of rooms, which **may potentially affect their marketability**.

**Price**

<iframe width="100%" height="438" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2tk_2gAqSRQgO5byAclakHBySDxHvMzHHOoP18DHYmLLUcGzf6e_1sC4hXGTvE7wwWVc8KEjzkD7U/pubchart?oid=474760295&amp;format=interactive"></iframe>

<style type="text/css">
caption {margin-bottom: 10px;}
.tg  {width: 100%;}
.tg .tg-3z1b{padding:0px 20px;border-color:#000000;text-align:right;vertical-align:top}
.tg .tg-guek{padding:0px 20px;background-color:#e50914;border-color:#000000;color:#ffffff;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-0pky{padding:0px 20px;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-dvpl{padding:0px 20px;border-color:#000000;text-align:right;vertical-align:top}
.tg .tg-a0bk{padding:0px 20px;border-color:#000000;font-weight:bold;text-align:left;vertical-align:middle}
.tg .tg-ich0{padding:0px 20px;border-color:#000000;text-align:right;vertical-align:middle}
</style>
<table class="tg">
<tbody>
  <tr>
    <td class="tg-a0bk">Count</td>
    <td class="tg-ich0">4,464</td>
    <td class="tg-a0bk">Standard Deviation</td>
    <td class="tg-ich0">RM1,354,048</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Minimum</td>
    <td class="tg-ich0">RM408</td>
    <td class="tg-a0bk">Coef. of Variation</td>
    <td class="tg-ich0">82.66%</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Maximum</td>
    <td class="tg-ich0">RM17,500,000</td>
    <td class="tg-a0bk">Skewness</td>
    <td class="tg-ich0">2.30</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Mean</td>
    <td class="tg-ich0">RM1,638,087</td>
    <td class="tg-a0bk">Q1</td>
    <td class="tg-ich0">RM680,000</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Median</td>
    <td class="tg-ich0">RM1,230,000</td>
    <td class="tg-a0bk">Q3</td>
    <td class="tg-ich0">RM2,200,000</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Mode</td>
    <td class="tg-ich0">RM1,200,000</td>
    <td class="tg-a0bk">IQR</td>
    <td class="tg-ich0">RM1,520,000</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Range</td>
    <td class="tg-ich0">RM17,499,592</td>
    <td class="tg-a0bk">Lower Limit</td>
    <td class="tg-ich0">-RM1,600,000</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Variance</td>
    <td class="tg-ich0">1,833,445,632,479</td>
    <td class="tg-a0bk">Upper Limit</td>
    <td class="tg-ich0">RM4,480,000</td>
  </tr>
</tbody>
</table>

**Size**

<iframe width="100%" height="438" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2tk_2gAqSRQgO5byAclakHBySDxHvMzHHOoP18DHYmLLUcGzf6e_1sC4hXGTvE7wwWVc8KEjzkD7U/pubchart?oid=2095399164&amp;format=interactive"></iframe>

<table class="tg">
<tbody>
  <tr>
    <td class="tg-a0bk">Count</td>
    <td class="tg-ich0">4,464</td>
    <td class="tg-a0bk">Standard Deviation</td>
    <td class="tg-ich0">12,051 sqft</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Minimum</td>
    <td class="tg-ich0">17 sqft</td>
    <td class="tg-a0bk">Coef. of Variation</td>
    <td class="tg-ich0">551.16%</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Maximum</td>
    <td class="tg-ich0">790,000 sqft</td>
    <td class="tg-a0bk">Skewness</td>
    <td class="tg-ich0">62.91036701</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Mean</td>
    <td class="tg-ich0">2,187 sqft</td>
    <td class="tg-a0bk">Q1</td>
    <td class="tg-ich0">1,067 sqft</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Median</td>
    <td class="tg-ich0">1,540 sqft</td>
    <td class="tg-a0bk">Q3</td>
    <td class="tg-ich0">2,499 sqft</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Mode</td>
    <td class="tg-ich0">1,650 sqft</td>
    <td class="tg-a0bk">IQR</td>
    <td class="tg-ich0">1,432 sqft</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Range</td>
    <td class="tg-ich0">789,983 sqft</td>
    <td class="tg-a0bk">Lower Limit</td>
    <td class="tg-ich0">-1,081 sqft</td>
  </tr>
  <tr>
    <td class="tg-a0bk">Variance</td>
    <td class="tg-ich0">145,237,347</td>
    <td class="tg-a0bk">Upper Limit</td>
    <td class="tg-ich0">4,646 sqft</td>
  </tr>
</tbody>
</table>

Through descriptive statistics, it was found that both the `price` and `size` variables had a *positively skewed* data distribution. Therefore, the **median** will be used as the measure of central tendency for these variables.

### Priority properties

Next, let’s explore the property characteristics and split them into groups based on the median price of each property location: **luxury properties**, which belong to the higher price range (Q3-Q4), and **affordable properties**, which fall inside the lower price range (Q1-Q2). This approach takes into consideration the market values of different locations, which are assumed to provide a more accurate representation of the *land values*.

<table class="tg">
<caption><strong>Luxury properties</strong></caption>
<tbody>
  <tr>
    <td class="tg-guek">location</td>
    <td class="tg-guek">M price</td>
    <td class="tg-guek">#</td>
  </tr>
  <tr>
    <td class="tg-0pky">ADIVA Desa ParkCity</td>
    <td class="tg-dvpl">RM2,400,000</td>
    <td class="tg-3z1b">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">Ampang Hilir</td>
    <td class="tg-dvpl">RM2,929,600</td>
    <td class="tg-3z1b">52</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bangsar</td>
    <td class="tg-dvpl">RM2,525,000</td>
    <td class="tg-3z1b">134</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bukit Kiara</td>
    <td class="tg-dvpl">RM4,988,888</td>
    <td class="tg-3z1b">4</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bukit Tunku (Kenny Hills)</td>
    <td class="tg-dvpl">RM2,240,000</td>
    <td class="tg-3z1b">16</td>
  </tr>
  <tr>
    <td class="tg-0pky">City Centre</td>
    <td class="tg-dvpl">RM1,780,000</td>
    <td class="tg-3z1b">57</td>
  </tr>
  <tr>
    <td class="tg-0pky">Damansara Heights</td>
    <td class="tg-dvpl">RM2,315,000</td>
    <td class="tg-3z1b">106</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">Desa ParkCity</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM1,900,000</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">316</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">Federal Hill</td>
    <td class="tg-dvpl">RM3,300,000</td>
    <td class="tg-3z1b">3</td>
  </tr>
  <tr>
    <td class="tg-0pky">KL Sentral</td>
    <td class="tg-dvpl">RM1,800,000</td>
    <td class="tg-3z1b">63</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">KLCC</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM1,900,000</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">562</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">Mont Kiara</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM1,830,000</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">656</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">OUG</td>
    <td class="tg-dvpl">RM1,700,000</td>
    <td class="tg-3z1b">15</td>
  </tr>
  <tr>
    <td class="tg-0pky">SEMARAK</td>
    <td class="tg-dvpl">RM3,500,000</td>
    <td class="tg-3z1b">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">Sri Hartamas</td>
    <td class="tg-dvpl">RM3,100,000</td>
    <td class="tg-3z1b">81</td>
  </tr>
  <tr>
    <td class="tg-0pky">Taman Melawati</td>
    <td class="tg-dvpl">RM1,700,000</td>
    <td class="tg-3z1b">41</td>
  </tr>
</tbody>
</table>

<table class="tg">
<caption><strong>Affordable properties</strong></caption>
<tbody>
  <tr>
    <td class="tg-guek">location</td>
    <td class="tg-guek">M price</td>
    <td class="tg-guek">#</td>
  </tr>
  <tr>
    <td class="tg-0pky">Alam Damai</td>
    <td class="tg-dvpl">RM880,000</td>
    <td class="tg-3z1b">1</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bandar Damai Perdana</td>
    <td class="tg-dvpl">RM657,000</td>
    <td class="tg-3z1b">6</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bandar Menjalara</td>
    <td class="tg-dvpl">RM838,000</td>
    <td class="tg-3z1b">23</td>
  </tr>
  <tr>
    <td class="tg-0pky">Bangsar South</td>
    <td class="tg-dvpl">RM780,000</td>
    <td class="tg-3z1b">59</td>
  </tr>
  <tr>
    <td class="tg-0pky">Batu Caves</td>
    <td class="tg-dvpl">RM676,775</td>
    <td class="tg-3z1b">23</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">Jalan Klang Lama</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM657,500</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">172</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">Kepong</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM798,000</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">179</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">KL City</td>
    <td class="tg-dvpl">RM880,000</td>
    <td class="tg-3z1b">39</td>
  </tr>
  <tr>
    <td class="tg-0pky">Pandan Indah</td>
    <td class="tg-dvpl">RM828,000</td>
    <td class="tg-3z1b">5</td>
  </tr>
  <tr>
    <td class="tg-0pky">Pantai</td>
    <td class="tg-dvpl">RM627,500</td>
    <td class="tg-3z1b">24</td>
  </tr>
  <tr>
    <td class="tg-0pky">Puchong</td>
    <td class="tg-dvpl">RM825,000</td>
    <td class="tg-3z1b">4</td>
  </tr>
  <tr>
    <td class="tg-0pky">Segambut</td>
    <td class="tg-dvpl">RM820,000</td>
    <td class="tg-3z1b">58</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="color: #e50914;font-weight: bold;">Sentul</span></td>
    <td class="tg-dvpl"><span style="color: #e50914;font-weight: bold;">RM800,000</span></td>
    <td class="tg-3z1b"><span style="color: #e50914;font-weight: bold;">104</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">Sri Petaling</td>
    <td class="tg-dvpl">RM795,000</td>
    <td class="tg-3z1b">47</td>
  </tr>
  <tr>
    <td class="tg-0pky">Titiwangsa</td>
    <td class="tg-dvpl">RM625,000</td>
    <td class="tg-3z1b">8</td>
  </tr>
  <tr>
    <td class="tg-0pky">Wangsa Maju</td>
    <td class="tg-dvpl">RM710,000</td>
    <td class="tg-3z1b">78</td>
  </tr>
</tbody>
</table>

Then, the focus was placed on the top 3 locations with *the highest number of listed properties*, both luxury and affordable properties. These locations were determined to be **priority properties** due to their alignment with the company's mission of providing users and tenants with a diverse range of property options. By considering the number of listed properties as a reliable indicator, the company ensures that users have a wide range of choices in these locations.



## Finding the right price

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.

## Recommendations

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.