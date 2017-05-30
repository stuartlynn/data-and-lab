---
layout: post
title: "Charleston 1"
date: 2017-05-30 16:04:05
image: '/assets/img/'
description:
main-class: 'DEMOGRAPHICS'
color:
tags:
- polygon
categories:
twitter_text:
introduction: '2000 Census Tract Data for Charleston, SC MSA and counties'
---
2000 Census Tract Data for Charleston, SC MSA and counties. Download the data [here](https://s3.amazonaws.com/geoda/data/CharlestonMSA.zip).  
Type = Polygon file  
Observations = 117  
Variables = 30  
(aggr.) = variables based on aggregate data  

**Source**  
2000 Census, Summary File 3. Available at http://factfinder.census.gov. Note that the poverty variable names can be easily confused: pov_pop is the reference populat ion (i.e. total population); pov_tot is all poor persons.  

Variable Name | Census Name | Description
---|---|---
FIPS | GEO_ID | FIPS Code
msa | Added | MSA Name
tot_pop | P001001 | Total population: Total
pop_16 | P008 (aggr.) | Total population: Under 16
pop_65 | P008 (aggr.) | Total population: 65+
white# |P007003 | Total population: Not Hispanic or Latino; White alone
black# | P007004 | Total population: Not Hispanic or Latino; Black or African American alone
asian# | P007006 | Total population: Not Hispanic or Latino; Asian alone
hisp# | P007010 | Total population: Hispanic or Latino
multi_ra | P007009 | Total population: Not Hispanic or Latino; Two or more races
males | P008002 | Total population: Male
females | P008041 | Total population: Female
male1664 | P008 (aggr.) | Total population: Male working age 16-64
fem1664 | P008 (aggr.) | Total population: Female working age 16-64
empl16 | P031001 | Workers 16 years and over: Total
emp_away | P031002 | Workers 16 years and over: Did not work at home
emp_home | P031015 | Workers 16 years and over: Worked at home
emp_29 | P031 | Workers 16 years and over: Did not work at home; Travel time to work; Less than 30 minutes
emp_30 | P031 | Workers 16 years and over: Did not work at home; Travel time to work; 30 minutes or more
emp16_2 | P050001 | Employed civilian population 16 years and over: Total
emp_male | P050002 | Employed civilian population 16 years and over: Male
emp_fem | P050049 | Employed civilian population 16 years and over: Female
occ_man | P050 (aggr.) | Employed civilian population 16 years and over: Production occupations
occ_off1 | P050 (aggr.) | Employed civilian population 16 years and over: Office (001-219 except 020, 021)
occ_info | P050 (aggr.) | Employed civilian population 16 years and over: Computer and mathematical occupations
hh_inc | P053001 | Households: Median household income in 1999
pov_pop* | P087001 | Population for whom poverty status is determined: Total Population
pov_tot* | P087002 | Population for whom poverty status is determined: Income in 1999 below poverty level
hsg_val | H085001 | Owner-occupied housing units: Median value
polyid | | Unique ID
