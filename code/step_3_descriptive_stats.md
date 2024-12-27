---
title: "VCAS-I Efficiency"
author: "Jonathan Salas"
date: "Last Updated 26 December, 2024"
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

Hypotheses:

1) rove_per_app and rove_vs_proc with x axis as patient number to hopefully show a decreasing trend for both; i.e., you can 
  do lots of applications in a short period of time & ablation time is small relative to procedure time as the physician
  becomes more comfortable with our system
  
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
## ! For variable `procedure_time` (`studyID = "VCAS-II"`) and "min" statistic: no
##   non-missing arguments to min; returning Inf
## ! For variable `procedure_time` (`studyID = "VCAS-II"`) and "max" statistic: no
##   non-missing arguments to max; returning -Inf
```

```{=html}
<div id="xrihjjjypk" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>#xrihjjjypk table {
  font-family: system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#xrihjjjypk thead, #xrihjjjypk tbody, #xrihjjjypk tfoot, #xrihjjjypk tr, #xrihjjjypk td, #xrihjjjypk th {
  border-style: none;
}

#xrihjjjypk p {
  margin: 0;
  padding: 0;
}

#xrihjjjypk .gt_table {
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

#xrihjjjypk .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}

#xrihjjjypk .gt_title {
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

#xrihjjjypk .gt_subtitle {
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

#xrihjjjypk .gt_heading {
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

#xrihjjjypk .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#xrihjjjypk .gt_col_headings {
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

#xrihjjjypk .gt_col_heading {
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

#xrihjjjypk .gt_column_spanner_outer {
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

#xrihjjjypk .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#xrihjjjypk .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#xrihjjjypk .gt_column_spanner {
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

#xrihjjjypk .gt_spanner_row {
  border-bottom-style: hidden;
}

#xrihjjjypk .gt_group_heading {
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

#xrihjjjypk .gt_empty_group_heading {
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

#xrihjjjypk .gt_from_md > :first-child {
  margin-top: 0;
}

#xrihjjjypk .gt_from_md > :last-child {
  margin-bottom: 0;
}

#xrihjjjypk .gt_row {
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

#xrihjjjypk .gt_stub {
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

#xrihjjjypk .gt_stub_row_group {
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

#xrihjjjypk .gt_row_group_first td {
  border-top-width: 2px;
}

#xrihjjjypk .gt_row_group_first th {
  border-top-width: 2px;
}

#xrihjjjypk .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#xrihjjjypk .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#xrihjjjypk .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#xrihjjjypk .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#xrihjjjypk .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#xrihjjjypk .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#xrihjjjypk .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}

#xrihjjjypk .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#xrihjjjypk .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#xrihjjjypk .gt_footnotes {
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

#xrihjjjypk .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#xrihjjjypk .gt_sourcenotes {
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

#xrihjjjypk .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#xrihjjjypk .gt_left {
  text-align: left;
}

#xrihjjjypk .gt_center {
  text-align: center;
}

#xrihjjjypk .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#xrihjjjypk .gt_font_normal {
  font-weight: normal;
}

#xrihjjjypk .gt_font_bold {
  font-weight: bold;
}

#xrihjjjypk .gt_font_italic {
  font-style: italic;
}

#xrihjjjypk .gt_super {
  font-size: 65%;
}

#xrihjjjypk .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}

#xrihjjjypk .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#xrihjjjypk .gt_indent_1 {
  text-indent: 5px;
}

#xrihjjjypk .gt_indent_2 {
  text-indent: 10px;
}

#xrihjjjypk .gt_indent_3 {
  text-indent: 15px;
}

#xrihjjjypk .gt_indent_4 {
  text-indent: 20px;
}

#xrihjjjypk .gt_indent_5 {
  text-indent: 25px;
}

#xrihjjjypk .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}

#xrihjjjypk div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
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
<td headers="n" class="gt_row gt_center">22</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">70 (54)</td>
<td headers="stat_1" class="gt_row gt_center">92 (47)</td>
<td headers="stat_2" class="gt_row gt_center">12 (7)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">76 [20-105]</td>
<td headers="stat_1" class="gt_row gt_center">95 [58-128]</td>
<td headers="stat_2" class="gt_row gt_center">10 [8-20]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3, 165</td>
<td headers="stat_1" class="gt_row gt_center">10, 165</td>
<td headers="stat_2" class="gt_row gt_center">3, 20</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">5</td>
<td headers="stat_1" class="gt_row gt_center">5</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">numberlesions</td>
<td headers="n" class="gt_row gt_center">22</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">15 (11)</td>
<td headers="stat_1" class="gt_row gt_center">20 (8)</td>
<td headers="stat_2" class="gt_row gt_center">2 (1)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">18 [3-21]</td>
<td headers="stat_1" class="gt_row gt_center">20 [16-26]</td>
<td headers="stat_2" class="gt_row gt_center">2 [1-3]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1, 33</td>
<td headers="stat_1" class="gt_row gt_center">7, 33</td>
<td headers="stat_2" class="gt_row gt_center">1, 3</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">5</td>
<td headers="stat_1" class="gt_row gt_center">5</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">procedure_time</td>
<td headers="n" class="gt_row gt_center">9</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">13,100 (4,630)</td>
<td headers="stat_1" class="gt_row gt_center">13,100 (4,630)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">11,340 [9,600-17,100]</td>
<td headers="stat_1" class="gt_row gt_center">11,340 [9,600-17,100]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">8,760, 21,600</td>
<td headers="stat_1" class="gt_row gt_center">8,760, 21,600</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">18</td>
<td headers="stat_1" class="gt_row gt_center">12</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time</td>
<td headers="n" class="gt_row gt_center">25</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1,657 (1,267)</td>
<td headers="stat_1" class="gt_row gt_center">2,116 (1,097)</td>
<td headers="stat_2" class="gt_row gt_center">203 (189)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1,734 [463-2,594]</td>
<td headers="stat_1" class="gt_row gt_center">2,075 [1,338-2,808]</td>
<td headers="stat_2" class="gt_row gt_center">167 [57-332]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">11, 3,965</td>
<td headers="stat_1" class="gt_row gt_center">304, 3,965</td>
<td headers="stat_2" class="gt_row gt_center">11, 484</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">2</td>
<td headers="stat_1" class="gt_row gt_center">2</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time</td>
<td headers="n" class="gt_row gt_center">19</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">4,113 (2,379)</td>
<td headers="stat_1" class="gt_row gt_center">4,113 (2,379)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3,360 [2,173-5,536]</td>
<td headers="stat_1" class="gt_row gt_center">3,360 [2,173-5,536]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">946, 10,800</td>
<td headers="stat_1" class="gt_row gt_center">946, 10,800</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">8</td>
<td headers="stat_1" class="gt_row gt_center">2</td>
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
<td headers="stat_0" class="gt_row gt_center">17 (63%)</td>
<td headers="stat_1" class="gt_row gt_center">17 (81%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    non-ischemic</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">4 (15%)</td>
<td headers="stat_1" class="gt_row gt_center">4 (19%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">therapy</td>
<td headers="n" class="gt_row gt_center">26</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_20x5_kissing</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">3 (12%)</td>
<td headers="stat_1" class="gt_row gt_center">0 (0%)</td>
<td headers="stat_2" class="gt_row gt_center">3 (50%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_20x5_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">9 (35%)</td>
<td headers="stat_1" class="gt_row gt_center">6 (30%)</td>
<td headers="stat_2" class="gt_row gt_center">3 (50%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    15kv_3x12_uni</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">14 (54%)</td>
<td headers="stat_1" class="gt_row gt_center">14 (70%)</td>
<td headers="stat_2" class="gt_row gt_center">0 (0%)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1</td>
<td headers="stat_1" class="gt_row gt_center">1</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">dwell_time_min</td>
<td headers="n" class="gt_row gt_center">19</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">69 (40)</td>
<td headers="stat_1" class="gt_row gt_center">69 (40)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">56 [36-92]</td>
<td headers="stat_1" class="gt_row gt_center">56 [36-92]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">16, 180</td>
<td headers="stat_1" class="gt_row gt_center">16, 180</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">8</td>
<td headers="stat_1" class="gt_row gt_center">2</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">rove_time_min</td>
<td headers="n" class="gt_row gt_center">25</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">28 (21)</td>
<td headers="stat_1" class="gt_row gt_center">35 (18)</td>
<td headers="stat_2" class="gt_row gt_center">3 (3)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">29 [8-43]</td>
<td headers="stat_1" class="gt_row gt_center">35 [22-47]</td>
<td headers="stat_2" class="gt_row gt_center">3 [1-6]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">0, 66</td>
<td headers="stat_1" class="gt_row gt_center">5, 66</td>
<td headers="stat_2" class="gt_row gt_center">0, 8</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">2</td>
<td headers="stat_1" class="gt_row gt_center">2</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">app_per_rove</td>
<td headers="n" class="gt_row gt_center">22</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">4.3 (4.6)</td>
<td headers="stat_1" class="gt_row gt_center">2.7 (1.0)</td>
<td headers="stat_2" class="gt_row gt_center">8.5 (7.6)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">2.7 [2.2-4.0]</td>
<td headers="stat_1" class="gt_row gt_center">2.6 [2.2-3.6]</td>
<td headers="stat_2" class="gt_row gt_center">6.4 [1.8-16.4]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">0.3, 19.1</td>
<td headers="stat_1" class="gt_row gt_center">0.3, 4.0</td>
<td headers="stat_2" class="gt_row gt_center">1.1, 19.1</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">5</td>
<td headers="stat_1" class="gt_row gt_center">5</td>
<td headers="stat_2" class="gt_row gt_center">0</td></tr>
    <tr><td headers="label" class="gt_row gt_left">irrigation_delivered</td>
<td headers="n" class="gt_row gt_center">19</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">411 (238)</td>
<td headers="stat_1" class="gt_row gt_center">411 (238)</td>
<td headers="stat_2" class="gt_row gt_center">NA (NA)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">336 [217-554]</td>
<td headers="stat_1" class="gt_row gt_center">336 [217-554]</td>
<td headers="stat_2" class="gt_row gt_center">NA [NA-NA]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">95, 1,080</td>
<td headers="stat_1" class="gt_row gt_center">95, 1,080</td>
<td headers="stat_2" class="gt_row gt_center">Inf, -Inf</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">8</td>
<td headers="stat_1" class="gt_row gt_center">2</td>
<td headers="stat_2" class="gt_row gt_center">6</td></tr>
    <tr><td headers="label" class="gt_row gt_left">energy_on_time</td>
<td headers="n" class="gt_row gt_center">19</td>
<td headers="stat_0" class="gt_row gt_center"><br /></td>
<td headers="stat_1" class="gt_row gt_center"><br /></td>
<td headers="stat_2" class="gt_row gt_center"><br /></td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Mean (SD)</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">12 (8)</td>
<td headers="stat_1" class="gt_row gt_center">14 (7)</td>
<td headers="stat_2" class="gt_row gt_center">2 (1)</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Median [Q1-Q3]</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">12 [5-17]</td>
<td headers="stat_1" class="gt_row gt_center">14 [9-19]</td>
<td headers="stat_2" class="gt_row gt_center">2 [1-3]</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Min, Max</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">1, 25</td>
<td headers="stat_1" class="gt_row gt_center">2, 25</td>
<td headers="stat_2" class="gt_row gt_center">1, 3</td></tr>
    <tr><td headers="label" class="gt_row gt_left">    Unknown</td>
<td headers="n" class="gt_row gt_center"><br /></td>
<td headers="stat_0" class="gt_row gt_center">8</td>
<td headers="stat_1" class="gt_row gt_center">5</td>
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

# VCAS-I Plots

## Make Mapping Data

Make temporary mapping data.



## Irrigation Delivered

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-7-1.png)<!-- -->

## Ablation Time

#### Line Plot

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-8-1.png)<!-- -->

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-9-1.png)<!-- -->

### Energy On Time

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-10-1.png)<!-- -->

# VCAS-II Plots

## Make Mapping Data

Make temporary mapping data.



## Ablation Time

#### Line Plot


```
## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'
```

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-12-1.png)<!-- -->

```
## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'
```

#### Box Plots

![](step_3_descriptive_stats_files/figure-html/unnamed-chunk-13-1.png)<!-- -->

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
## [1] "Thu Dec 26 21:48:40 2024"
```
