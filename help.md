<div class="page_container" markdown="1" style="font-size: x-small;">

<div id="toc_container" markdown="1">

<span class="toc_span">adc_config</span>
<span class="toc_span_items">[Misc ↓](#misc)</span>
<span class="toc_span_items">[Params ↓](#parameters)</span>
<span class="toc_span_items">[Ports ↓](#ports)</span>

</div>

This component configures the ADC unit either from parameters or JSON
string input.

<div class="section_heading" markdown="1">

<span id="parameters" class="toc_span">Parameters</span>

<div class="toc_span_items" markdown="1">

[Top ↑](#toc_container)

</div>

<div class="toc_span_items" markdown="1">

[Misc ↓](#misc)

</div>

<div class="toc_span_items" markdown="1">

[Ports ↓](#ports)

</div>

</div>

|                    |         |                                                                                                                                     |         |      |            |
|--------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|---------|------|------------|
| name               | type    | description                                                                                                                         | default | min. | max.       |
| device_id          | integer | The ADC Device number to be configured. For internal ADCs, this is the unit. For external ADCs, this is the address enumeration.    | 0       | 0    | 9          |
| f_s_hz             | integer | Total sampling frequency in Hz. With n channels enabled, the sampling frequency of each channel is f_s_hz/n Hz.                     | 1000    | 100  | 1000000000 |
| mode               | boolean | The ADC conversion mode. False for Single-shot. True for Continuous.                                                                | 0       | 0    | 1          |
| channel\_\[0..15\] | integer | Pin mapping for individual channels of this ADC instance/unit. For fixed-mapped ADC, any non-negative number means enabled channel. | -1      | -1   | 999        |

<div class="section_heading" markdown="1">

<span id="ports" class="toc_span">Ports</span>
<span class="toc_span_items">[Top ↑](#toc_container)</span>
<span class="toc_span_items">[Misc ↓](#misc)</span>
<span class="toc_span_items">[Params ↑](#parameters)</span>

</div>

<table class="table">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="header">
<th>In Ev.</th>
<th>Description</th>
</tr>
&#10;<tr class="odd">
<th class="ports">init</th>
<th>Initialise the ADC unit with the configuration defined in either the
parameters or the <a href="#%5BIn%5DJSON">JSON</a> input port.</th>
</tr>
<tr class="even">
<th>Data In</th>
<th>Description</th>
</tr>
<tr class="odd">
<th class="ports"><span id="[In]JSON">JSON</span></th>
<th>Alternative definition to the parameters to override. The format of
it is:
<table>
<tbody>
<tr class="odd" style="background-color:#333333;">
<td><p><span style="color:white;">{"id":</span> <span
style="color:red;">0</span> <span style="color:white;">,"fs":</span>
<span style="color:red;">1000</span> <span
style="color:white;">,"m":</span> <span style="color:red;">0</span>
<span style="color:white;">,"c0":</span> <span
style="color:red;">-1</span> <span style="color:white;">,"c1":</span>
<span style="color:red;">123</span> <span
style="color:white;">,"c2":</span> <span style="color:red;">-1</span>
<span style="color:white;">,"c3":</span> <span
style="color:red;">0</span> <span style="color:white;">, ...
,"c15":</span> <span style="color:red;">-1</span> <span
style="color:white;">}</span></p></td>
</tr>
</tbody>
</table></th>
</tr>
<tr class="even">
<th>Data Out</th>
<th>Description</th>
</tr>
<tr class="odd">
<th>Out Ev.</th>
<th>Description</th>
</tr>
<tr class="even">
<th class="ports"><span id="[Out]done">--</span></th>
<th>Triggerred when the configuration is completed without any
error</th>
</tr>
<tr class="odd">
<th class="ports"><span id="[Out]error">error</span></th>
<th>Triggerred when:
<ol>
<li><span>the same unit is already initialised</span></li>
<li><span>the parameters are invalid</span></li>
<li><span>the JSON port gives invalid format</span></li>
</ol></th>
</tr>
</tbody>
</table>

<div class="section_heading" markdown="1">

<span id="misc" class="toc_span">Misc</span>
<span class="toc_span_items">[Top ↑](#toc_container)</span>
<span class="toc_span_items">[Ports ↑](#ports)</span>
<span class="toc_span_items">[Params ↑](#parameters)</span>

</div>

|                   |        |                        |                                                         |     |     |
|-------------------|--------|------------------------|---------------------------------------------------------|-----|-----|
| **State Machine** | None   |                        |                                                         |     |     |
| **Toolbox**       | Core   | **Version**            | v1.0.                                                   |     |     |
| **Licence Type**  | LGPLv3 | **Component Supplier** | [inx ltd.](http://www.inx-systems.net){target="_blank"} |     |     |
| **Minumum DCC**   | A0000  | **Profiles**           | All.                                                    |     |     |

</div>
