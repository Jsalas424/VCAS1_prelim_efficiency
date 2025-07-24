---
title: "VCAS-I Efficiency: Procedural Analysis Set"
author: "Jonathan Salas"
date: "Last Updated 09 June, 2025"
output: 
  html_document: 
    df_print: kable
    fig_height: 6
    keep_md: true
---



# Start with a clean slate



# Import - Point to the correct raw data directory



## load Subject Data



# Descriptive Statistics

Analysis Plan:
- histoplots of continuous variables - as of 7/30/24 this was useless to do, shows nothing at all due to small sample
- loess plots of continuous variables; x-axis is each procedure aligned in termporal order
- box plots
- we do procedure time vs rove time "proc_vs_rove" 

## The numbers


```
## The following warnings were returned during `as_gt()`:
## ! For variable `dwell_time` (`studyID = "VCAS-II"`) and "min" statistic: no
##   non-missing arguments to min; returning Inf
## ! For variable `dwell_time` (`studyID = "VCAS-II"`) and "max" statistic: no
##   non-missing arguments to max; returning -Inf
## ! For variable `dwell_time_min` (`studyID = "VCAS-II"`) and "min" statistic: no
##   non-missing arguments to min; returning Inf
## ! For variable `dwell_time_min` (`studyID = "VCAS-II"`) and "max" statistic: no
##   non-missing arguments to max; returning -Inf
## ! For variable `irrigation_delivered` (`studyID = "VCAS-II"`) and "min"
##   statistic: no non-missing arguments to min; returning Inf
## ! For variable `irrigation_delivered` (`studyID = "VCAS-II"`) and "max"
##   statistic: no non-missing arguments to max; returning -Inf
```

```{=html}
<div id="cjnhtgbdun" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#cjnhtgbdun table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#cjnhtgbdun thead, #cjnhtgbdun tbody, #cjnhtgbdun tfoot, #cjnhtgbdun tr, #cjnhtgbdun td, #cjnhtgbdun th {
  border-style: none;
}

#cjnhtgbdun p {
  margin: 0;
  padding: 0;
}

#cjnhtgbdun .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#cjnhtgbdun .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}

#cjnhtgbdun .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#cjnhtgbdun .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#cjnhtgbdun .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cjnhtgbdun .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cjnhtgbdun .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cjnhtgbdun .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#cjnhtgbdun .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#cjnhtgbdun .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#cjnhtgbdun .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#cjnhtgbdun .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#cjnhtgbdun .gt_spanner_row {
  border-bottom-style: hidden;
}

#cjnhtgbdun .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}

#cjnhtgbdun .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#cjnhtgbdun .gt_from_md > :first-child {
  margin-top: 0;
}

#cjnhtgbdun .gt_from_md > :last-child {
  margin-bottom: 0;
}

#cjnhtgbdun .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#cjnhtgbdun .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#cjnhtgbdun .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#cjnhtgbdun .gt_row_group_first td {
  border-top-width: 2px;
}

#cjnhtgbdun .gt_row_group_first th {
  border-top-width: 2px;
}

#cjnhtgbdun .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cjnhtgbdun .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#cjnhtgbdun .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#cjnhtgbdun .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cjnhtgbdun .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cjnhtgbdun .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#cjnhtgbdun .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}

#cjnhtgbdun .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#cjnhtgbdun .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cjnhtgbdun .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cjnhtgbdun .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#cjnhtgbdun .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cjnhtgbdun .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#cjnhtgbdun .gt_left {
  text-align: left;
}

#cjnhtgbdun .gt_center {
  text-align: center;
}

#cjnhtgbdun .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#cjnhtgbdun .gt_font_normal {
  font-weight: normal;
}

#cjnhtgbdun .gt_font_bold {
  font-weight: bold;
}

#cjnhtgbdun .gt_font_italic {
  font-style: italic;
}

#cjnhtgbdun .gt_super {
  font-size: 65%;
}

#cjnhtgbdun .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}

#cjnhtgbdun .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#cjnhtgbdun .gt_indent_1 {
  text-indent: 5px;
}

#cjnhtgbdun .gt_indent_2 {
  text-indent: 10px;
}

#cjnhtgbdun .gt_indent_3 {
  text-indent: 15px;
}

#cjnhtgbdun .gt_indent_4 {
  text-indent: 20px;
}

#cjnhtgbdun .gt_indent_5 {
  text-indent: 25px;
}

#cjnhtgbdun .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}

#cjnhtgbdun div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
  height: 0px !important;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;Characteristic&lt;/strong&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>Characteristic</strong></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;N&lt;/strong&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>N</strong></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;Overall&lt;/strong&gt;&lt;br /&gt;&#10;N = 27&lt;/span&gt;&lt;span class=&quot;gt_footnote_marks&quot; style=&quot;white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;&quot;&gt;&lt;sup&gt;1&lt;/sup&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>Overall</strong><br />
N = 27</span><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;VCAS-I&lt;/strong&gt;&lt;br /&gt;&#10;N = 21&lt;/span&gt;&lt;span class=&quot;gt_footnote_marks&quot; style=&quot;white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;&quot;&gt;&lt;sup&gt;1&lt;/sup&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>VCAS-I</strong><br />
N = 21</span><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;VCAS-II&lt;/strong&gt;&lt;br /&gt;&#10;N = 6&lt;/span&gt;&lt;span class=&quot;gt_footnote_marks&quot; style=&quot;white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;&quot;&gt;&lt;sup&gt;1&lt;/sup&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>VCAS-II</strong><br />
N = 6</span><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="label" class="gt_row gt_left">numberapplications</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">81 (70)</td>
<td headers="stat_1" class="gt_row gt_center">100 (67)</td>
<td headers="stat_2" class="gt_row gt_center">12 (7)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">81 [20-106]</td>
<td headers="stat_1" class="gt_row gt_center">95 [75-116]</td>
<td headers="stat_2" class="gt_row gt_center">10 [8-20]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3, 321</td>
<td headers="stat_1" class="gt_row gt_center">10, 321</td>
<td headers="stat_2" class="gt_row gt_center">3, 20</td></tr>
    <tr><td headers="label" class="gt_row gt_left">numberlesions</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">17 (13)</td>
<td headers="stat_1" class="gt_row gt_center">21 (12)</td>
<td headers="stat_2" class="gt_row gt_center">3 (1)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">19 [4-21]</td>
<td headers="stat_1" class="gt_row gt_center">20 [16-23]</td>
<td headers="stat_2" class="gt_row gt_center">3 [2-4]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1, 64</td>
<td headers="stat_1" class="gt_row gt_center">4, 64</td>
<td headers="stat_2" class="gt_row gt_center">1, 4</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1,665 (1,222)</td>
<td headers="stat_1" class="gt_row gt_center">2,083 (1,052)</td>
<td headers="stat_2" class="gt_row gt_center">203 (189)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1,734 [463-2,594]</td>
<td headers="stat_1" class="gt_row gt_center">2,075 [1,414-2,801]</td>
<td headers="stat_2" class="gt_row gt_center">167 [57-332]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">11, 3,965</td>
<td headers="stat_1" class="gt_row gt_center">304, 3,965</td>
<td headers="stat_2" class="gt_row gt_center">11, 484</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">4,000 (2,301)</td>
<td headers="stat_1" class="gt_row gt_center">4,000 (2,301)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3,360 [2,173-5,374]</td>
<td headers="stat_1" class="gt_row gt_center">3,360 [2,173-5,374]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">946, 10,800</td>
<td headers="stat_1" class="gt_row gt_center">946, 10,800</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">6</td>
<td headers="stat_1" class="gt_row gt_center">0</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">etiology</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    idiopathic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">6 (22%)</td>
<td headers="stat_1" class="gt_row gt_center">0 (0%)</td>
<td headers="stat_2" class="gt_row gt_center">6 (100%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    ischemic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">18 (67%)</td>
<td headers="stat_1" class="gt_row gt_center">18 (86%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    non-ischemic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3 (11%)</td>
<td headers="stat_1" class="gt_row gt_center">3 (14%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">therapy</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_20x5_kissing</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3 (11%)</td>
<td headers="stat_1" class="gt_row gt_center">0 (0%)</td>
<td headers="stat_2" class="gt_row gt_center">3 (50%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_20x5_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">9 (33%)</td>
<td headers="stat_1" class="gt_row gt_center">6 (29%)</td>
<td headers="stat_2" class="gt_row gt_center">3 (50%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_3x12_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">15 (56%)</td>
<td headers="stat_1" class="gt_row gt_center">15 (71%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time_min</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">67 (38)</td>
<td headers="stat_1" class="gt_row gt_center">67 (38)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">56 [36-90]</td>
<td headers="stat_1" class="gt_row gt_center">56 [36-90]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">16, 180</td>
<td headers="stat_1" class="gt_row gt_center">16, 180</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">6</td>
<td headers="stat_1" class="gt_row gt_center">0</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time_min</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">28 (20)</td>
<td headers="stat_1" class="gt_row gt_center">35 (18)</td>
<td headers="stat_2" class="gt_row gt_center">3 (3)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">29 [8-43]</td>
<td headers="stat_1" class="gt_row gt_center">35 [24-47]</td>
<td headers="stat_2" class="gt_row gt_center">3 [1-6]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">0, 66</td>
<td headers="stat_1" class="gt_row gt_center">5, 66</td>
<td headers="stat_2" class="gt_row gt_center">0, 8</td></tr>
    <tr><td headers="label" class="gt_row gt_left">app_per_rove</td>
<td headers="n" class="gt_row gt_center">27</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">4.3 (4.2)</td>
<td headers="stat_1" class="gt_row gt_center">3.1 (1.3)</td>
<td headers="stat_2" class="gt_row gt_center">8.5 (7.6)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3.0 [2.3-4.2]</td>
<td headers="stat_1" class="gt_row gt_center">2.8 [2.4-4.0]</td>
<td headers="stat_2" class="gt_row gt_center">6.4 [1.8-16.4]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">0.3, 19.1</td>
<td headers="stat_1" class="gt_row gt_center">0.3, 6.1</td>
<td headers="stat_2" class="gt_row gt_center">1.1, 19.1</td></tr>
    <tr><td headers="label" class="gt_row gt_left">irrigation_delivered</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">400 (230)</td>
<td headers="stat_1" class="gt_row gt_center">400 (230)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">336 [217-537]</td>
<td headers="stat_1" class="gt_row gt_center">336 [217-537]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">95, 1,080</td>
<td headers="stat_1" class="gt_row gt_center">95, 1,080</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">6</td>
<td headers="stat_1" class="gt_row gt_center">0</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">energy_on_time</td>
<td headers="n" class="gt_row gt_center">24</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">13 (10)</td>
<td headers="stat_1" class="gt_row gt_center">15 (10)</td>
<td headers="stat_2" class="gt_row gt_center">2 (1)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">14 [5-17]</td>
<td headers="stat_1" class="gt_row gt_center">14 [11-17]</td>
<td headers="stat_2" class="gt_row gt_center">2 [1-3]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1, 48</td>
<td headers="stat_1" class="gt_row gt_center">2, 48</td>
<td headers="stat_2" class="gt_row gt_center">1, 3</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3</td>
<td headers="stat_1" class="gt_row gt_center">0</td>
<td headers="stat_2" class="gt_row gt_center">3</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="5"><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span> <span class='gt_from_md'>n (%)</span></td>
    </tr>
  </tfoot>
</table>
</div>
```

### VCAS-I Only


```{=html}
<div id="ypolyymtun" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#ypolyymtun table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#ypolyymtun thead, #ypolyymtun tbody, #ypolyymtun tfoot, #ypolyymtun tr, #ypolyymtun td, #ypolyymtun th {
  border-style: none;
}

#ypolyymtun p {
  margin: 0;
  padding: 0;
}

#ypolyymtun .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#ypolyymtun .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}

#ypolyymtun .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#ypolyymtun .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#ypolyymtun .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ypolyymtun .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ypolyymtun .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#ypolyymtun .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#ypolyymtun .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#ypolyymtun .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#ypolyymtun .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#ypolyymtun .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#ypolyymtun .gt_spanner_row {
  border-bottom-style: hidden;
}

#ypolyymtun .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}

#ypolyymtun .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#ypolyymtun .gt_from_md > :first-child {
  margin-top: 0;
}

#ypolyymtun .gt_from_md > :last-child {
  margin-bottom: 0;
}

#ypolyymtun .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#ypolyymtun .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#ypolyymtun .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#ypolyymtun .gt_row_group_first td {
  border-top-width: 2px;
}

#ypolyymtun .gt_row_group_first th {
  border-top-width: 2px;
}

#ypolyymtun .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ypolyymtun .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#ypolyymtun .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#ypolyymtun .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ypolyymtun .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#ypolyymtun .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#ypolyymtun .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}

#ypolyymtun .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#ypolyymtun .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#ypolyymtun .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ypolyymtun .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#ypolyymtun .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#ypolyymtun .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#ypolyymtun .gt_left {
  text-align: left;
}

#ypolyymtun .gt_center {
  text-align: center;
}

#ypolyymtun .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#ypolyymtun .gt_font_normal {
  font-weight: normal;
}

#ypolyymtun .gt_font_bold {
  font-weight: bold;
}

#ypolyymtun .gt_font_italic {
  font-style: italic;
}

#ypolyymtun .gt_super {
  font-size: 65%;
}

#ypolyymtun .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}

#ypolyymtun .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#ypolyymtun .gt_indent_1 {
  text-indent: 5px;
}

#ypolyymtun .gt_indent_2 {
  text-indent: 10px;
}

#ypolyymtun .gt_indent_3 {
  text-indent: 15px;
}

#ypolyymtun .gt_indent_4 {
  text-indent: 20px;
}

#ypolyymtun .gt_indent_5 {
  text-indent: 25px;
}

#ypolyymtun .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}

#ypolyymtun div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
  height: 0px !important;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;Characteristic&lt;/strong&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>Characteristic</strong></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;N&lt;/strong&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>N</strong></span></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="&lt;span class='gt_from_md'&gt;&lt;strong&gt;VCAS-I&lt;/strong&gt;&lt;br /&gt;&#10;N = 21&lt;/span&gt;&lt;span class=&quot;gt_footnote_marks&quot; style=&quot;white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;&quot;&gt;&lt;sup&gt;1&lt;/sup&gt;&lt;/span&gt;"><span class='gt_from_md'><strong>VCAS-I</strong><br />
N = 21</span><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="label" class="gt_row gt_left">numberapplications</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">100 (67)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">95 [75-116]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">10, 321</td></tr>
    <tr><td headers="label" class="gt_row gt_left">numberlesions</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">21 (12)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">20 [16-23]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">4, 64</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">2,083 (1,052)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">2,075 [1,414-2,801]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">304, 3,965</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">4,000 (2,301)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">3,360 [2,173-5,374]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">946, 10,800</td></tr>
    <tr><td headers="label" class="gt_row gt_left">etiology</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    ischemic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">18 (86%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    non-ischemic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">3 (14%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">therapy</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_20x5_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">6 (29%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_3x12_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">15 (71%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time_min</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">67 (38)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">56 [36-90]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">16, 180</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time_min</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">35 (18)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">35 [24-47]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">5, 66</td></tr>
    <tr><td headers="label" class="gt_row gt_left">app_per_rove</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">3.07 (1.25)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">2.75 [2.41-3.95]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">0.29, 6.06</td></tr>
    <tr><td headers="label" class="gt_row gt_left">irrigation_delivered</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">400 (230)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">336 [217-537]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">95, 1,080</td></tr>
    <tr><td headers="label" class="gt_row gt_left">energy_on_time</td>
<td headers="n" class="gt_row gt_center">21</td>
<td headers="stat_1" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">15 (10)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">14 [11-17]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center">2, 48</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="3"><span class="gt_footnote_marks" style="white-space:nowrap;font-style:italic;font-weight:normal;line-height: 0;"><sup>1</sup></span> <span class='gt_from_md'>n (%)</span></td>
    </tr>
  </tfoot>
</table>
</div>
```

# VCAS-I Plots

## Make Mapping Data

Make temporary mapping data.



## Irrigation Delivered

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-7-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

## Ablation Time

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-9-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-10-1.png)<!-- -->

### Energy On Time

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-11-1.png)<!-- -->

# VCAS-II Plots

## Make Mapping Data

Make temporary mapping data.



## Ablation Time

#### Line Plot


```
## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'
```

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-13-1.png)<!-- -->

```
## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'
```

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-14-1.png)<!-- -->

# Version and Package Details


```
## [1] "R version 4.4.0 (2024-04-24) Puppy Cup"
```

```
## [1] "RStudio Version 2024.4.2.764 Chocolate Cosmos"
```

<div class="kable-table">

|          |package   |loadedversion |
|:---------|:---------|:-------------|
|cowplot   |cowplot   |1.1.3         |
|dplyr     |dplyr     |1.1.4         |
|ggplot2   |ggplot2   |3.5.1         |
|gtsummary |gtsummary |2.0.1         |
|MASS      |MASS      |7.3-61        |

</div>

# Detach Packages before moving on


```
## Warning: 'dplyr' namespace cannot be unloaded:
##   namespace 'dplyr' is imported by 'cards', 'gtsummary', 'tidyr', 'gt' so cannot be unloaded
```

# When were these files last rewritten?


```
## [1] "Mon Jun  9 18:19:49 2025"
```
