# Summary
Indicates a Studio widget or element with a particular color.

# Details
Each Studio theme has a color for each item, as well as a number of modifiers
corresponding to [StudioStyleGuideModifier][SSGM]. The color of an item can be
retrieved with [StudioTheme.GetColor](class:StudioTheme/GetColor).

The following table lists, for each theme, the current colors and their
variations:

[SSGM]: enum:StudioStyleGuideModifier

<table>
	<thead><tr><th>Item</th><th>Light</th><th>Dark</th></tr></thead>
	<tbody>
	<tr><td>MainBackground</td>                       <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>Titlebar</td>                             <td><div class="swatches" style="--0:#E3E3E3;--1:#E3E3E3;--2:#E3E3E3;--3:#E3E3E3;--4:#E3E3E3"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>Dropdown</td>                             <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>Tooltip</td>                              <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>Notification</td>                         <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>ScrollBar</td>                            <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#DBDBDB;--3:#E7E7E7;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#383838;--1:#383838;--2:#464646;--3:#222222;--4:#464646"></div></td></tr>
	<tr><td>ScrollBarBackground</td>                  <td><div class="swatches" style="--0:#EEEEEE;--1:#EEEEEE;--2:#EEEEEE;--3:#EEEEEE;--4:#EEEEEE"></div></td><td><div class="swatches" style="--0:#292929;--1:#292929;--2:#292929;--3:#292929;--4:#292929"></div></td></tr>
	<tr><td>TabBar</td>                               <td><div class="swatches" style="--0:#F2F2F2;--1:#F2F2F2;--2:#F2F2F2;--3:#F2F2F2;--4:#F2F2F2"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>Tab</td>                                  <td><div class="swatches" style="--0:#F2F2F2;--1:#FFFFFF;--2:#F2F2F2;--3:#F2F2F2;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#353535;--1:#252525;--2:#353535;--3:#353535;--4:#2A2A2A"></div></td></tr>
	<tr><td>RibbonTab</td>                            <td><div class="swatches" style="--0:#F3F3F3;--1:#FFFFFF;--2:#F3F3F3;--3:#F3F3F3;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#353535;--1:#2E2E2E;--2:#353535;--3:#353535;--4:#2E2E2E"></div></td></tr>
	<tr><td>RibbonTabTopBar</td>                      <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#35B5FF;--1:#35B5FF;--2:#35B5FF;--3:#35B5FF;--4:#35B5FF"></div></td></tr>
	<tr><td>Button</td>                               <td><div class="swatches" style="--0:#FFFFFF;--1:#E4EEFE;--2:#DBDBDB;--3:#FFFFFF;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#3C3C3C;--1:#00A2FF;--2:#292929;--3:#3C3C3C;--4:#424242"></div></td></tr>
	<tr><td>MainButton</td>                           <td><div class="swatches" style="--0:#E4EEFE;--1:#E4EEFE;--2:#DBDBDB;--3:#E4EEFE;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#00A2FF;--1:#00A2FF;--2:#0074BD;--3:#00A2FF;--4:#32B5FF"></div></td></tr>
	<tr><td>RibbonButton</td>                         <td><div class="swatches" style="--0:#FFFFFF;--1:#DBDBDB;--2:#DBDBDB;--3:#FFFFFF;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#1C1C1C;--2:#1C1C1C;--3:#2E2E2E;--4:#252525"></div></td></tr>
	<tr><td>ViewPortBackground</td>                   <td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#AAAAAA;--4:#AAAAAA"></div></td><td><div class="swatches" style="--0:#252525;--1:#252525;--2:#252525;--3:#252525;--4:#252525"></div></td></tr>
	<tr><td>InputFieldBackground</td>                 <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#E7E7E7;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#252525;--1:#252525;--2:#252525;--3:#353535;--4:#424242"></div></td></tr>
	<tr><td>Item</td>                                 <td><div class="swatches" style="--0:#FFFFFF;--1:#6894D9;--2:#FFFFFF;--3:#FFFFFF;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#0B5AAF;--2:#2E2E2E;--3:#2E2E2E;--4:#424242"></div></td></tr>
	<tr><td>TableItem</td>                            <td><div class="swatches" style="--0:#F5F5F5;--1:#6894D9;--2:#F5F5F5;--3:#F5F5F5;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#2A2A2A;--1:#0B5AAF;--2:#2A2A2A;--3:#2A2A2A;--4:#424242"></div></td></tr>
	<tr><td>CategoryItem</td>                         <td><div class="swatches" style="--0:#E9E9E9;--1:#E9E9E9;--2:#E9E9E9;--3:#E9E9E9;--4:#E9E9E9"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>GameSettingsTableItem</td>                <td><div class="swatches" style="--0:#F5F5F5;--1:#FFFFFF;--2:#F5F5F5;--3:#F5F5F5;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#2A2A2A;--1:#0B5AAF;--2:#2A2A2A;--3:#2A2A2A;--4:#424242"></div></td></tr>
	<tr><td>GameSettingsTooltip</td>                  <td><div class="swatches" style="--0:#757575;--1:#757575;--2:#757575;--3:#757575;--4:#757575"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>EmulatorBar</td>                          <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#252525"></div></td></tr>
	<tr><td>EmulatorDropDown</td>                     <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#424242"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#424242"></div></td></tr>
	<tr><td>ColorPickerFrame</td>                     <td><div class="swatches" style="--0:#EDEDED;--1:#EDEDED;--2:#EDEDED;--3:#EDEDED;--4:#EDEDED"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>CurrentMarker</td>                        <td><div class="swatches" style="--0:#00A2FF;--1:#00A2FF;--2:#00A2FF;--3:#00A2FF;--4:#00A2FF"></div></td><td><div class="swatches" style="--0:#424242;--1:#0B5AAF;--2:#424242;--3:#424242;--4:#424242"></div></td></tr>
	<tr><td>Border</td>                               <td><div class="swatches" style="--0:#B6B6B6;--1:#B6B6B6;--2:#B6B6B6;--3:#B6B6B6;--4:#B6B6B6"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>Shadow</td>                               <td><div class="swatches" style="--0:#EEEEEE;--1:#EEEEEE;--2:#EEEEEE;--3:#EEEEEE;--4:#EEEEEE"></div></td><td><div class="swatches" style="--0:#404040;--1:#404040;--2:#404040;--3:#404040;--4:#404040"></div></td></tr>
	<tr><td>Light</td>                                <td><div class="swatches" style="--0:#F3F3F3;--1:#F3F3F3;--2:#F3F3F3;--3:#F3F3F3;--4:#F3F3F3"></div></td><td><div class="swatches" style="--0:#404040;--1:#404040;--2:#404040;--3:#404040;--4:#404040"></div></td></tr>
	<tr><td>Dark</td>                                 <td><div class="swatches" style="--0:#A0A0A0;--1:#A0A0A0;--2:#A0A0A0;--3:#A0A0A0;--4:#A0A0A0"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>Mid</td>                                  <td><div class="swatches" style="--0:#EEEEEE;--1:#EEEEEE;--2:#EEEEEE;--3:#EEEEEE;--4:#EEEEEE"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>MainText</td>                             <td><div class="swatches" style="--0:#000000;--1:#FFFFFF;--2:#000000;--3:#787878;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#FFFFFF;--2:#CCCCCC;--3:#555555;--4:#FFFFFF"></div></td></tr>
	<tr><td>SubText</td>                              <td><div class="swatches" style="--0:#AAAAAA;--1:#CCCCCC;--2:#AAAAAA;--3:#787878;--4:#AAAAAA"></div></td><td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#555555;--4:#AAAAAA"></div></td></tr>
	<tr><td>TitlebarText</td>                         <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#C7C7C7;--4:#000000"></div></td><td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#555555;--4:#AAAAAA"></div></td></tr>
	<tr><td>BrightText</td>                           <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#E5E5E5;--1:#E5E5E5;--2:#E5E5E5;--3:#E5E5E5;--4:#E5E5E5"></div></td></tr>
	<tr><td>DimmedText</td>                           <td><div class="swatches" style="--0:#888888;--1:#CCCCCC;--2:#888888;--3:#888888;--4:#888888"></div></td><td><div class="swatches" style="--0:#666666;--1:#AAAAAA;--2:#666666;--3:#666666;--4:#666666"></div></td></tr>
	<tr><td>LinkText</td>                             <td><div class="swatches" style="--0:#35B5FF;--1:#35B5FF;--2:#35B5FF;--3:#35B5FF;--4:#35B5FF"></div></td><td><div class="swatches" style="--0:#35B5FF;--1:#35B5FF;--2:#35B5FF;--3:#35B5FF;--4:#35B5FF"></div></td></tr>
	<tr><td>WarningText</td>                          <td><div class="swatches" style="--0:#FF8000;--1:#FF8000;--2:#FF8000;--3:#FF8000;--4:#FF8000"></div></td><td><div class="swatches" style="--0:#FF8E3C;--1:#FF8E3C;--2:#FF8E3C;--3:#FF8E3C;--4:#FF8E3C"></div></td></tr>
	<tr><td>ErrorText</td>                            <td><div class="swatches" style="--0:#FF0000;--1:#FF0000;--2:#FF0000;--3:#FF0000;--4:#FF0000"></div></td><td><div class="swatches" style="--0:#FF4444;--1:#FF4444;--2:#FF4444;--3:#FF4444;--4:#FF4444"></div></td></tr>
	<tr><td>InfoText</td>                             <td><div class="swatches" style="--0:#0000FF;--1:#0000FF;--2:#0000FF;--3:#0000FF;--4:#0000FF"></div></td><td><div class="swatches" style="--0:#80D7FF;--1:#80D7FF;--2:#80D7FF;--3:#80D7FF;--4:#80D7FF"></div></td></tr>
	<tr><td>SensitiveText</td>                        <td><div class="swatches" style="--0:#800080;--1:#800080;--2:#800080;--3:#800080;--4:#800080"></div></td><td><div class="swatches" style="--0:#D15DFF;--1:#D15DFF;--2:#D15DFF;--3:#D15DFF;--4:#D15DFF"></div></td></tr>
	<tr><td>ScriptSideWidget</td>                     <td><div class="swatches" style="--0:#C0C0C0;--1:#C0C0C0;--2:#C0C0C0;--3:#C0C0C0;--4:#C0C0C0"></div></td><td><div class="swatches" style="--0:#252525;--1:#252525;--2:#252525;--3:#252525;--4:#252525"></div></td></tr>
	<tr><td>ScriptBackground</td>                     <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#252525;--1:#252525;--2:#252525;--3:#252525;--4:#252525"></div></td></tr>
	<tr><td>ScriptText</td>                           <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td></tr>
	<tr><td>ScriptSelectionText</td>                  <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#999999;--1:#999999;--2:#999999;--3:#999999;--4:#999999"></div></td></tr>
	<tr><td>ScriptSelectionBackground</td>            <td><div class="swatches" style="--0:#6EA1F1;--1:#6EA1F1;--2:#6EA1F1;--3:#6EA1F1;--4:#6EA1F1"></div></td><td><div class="swatches" style="--0:#2A2A2A;--1:#2A2A2A;--2:#2A2A2A;--3:#2A2A2A;--4:#2A2A2A"></div></td></tr>
	<tr><td>ScriptFindSelectionBackground</td>        <td><div class="swatches" style="--0:#F6B93F;--1:#F6B93F;--2:#F6B93F;--3:#F6B93F;--4:#F6B93F"></div></td><td><div class="swatches" style="--0:#FFF550;--1:#FFF550;--2:#FFF550;--3:#FFF550;--4:#FFF550"></div></td></tr>
	<tr><td>ScriptMatchingWordSelectionBackground</td><td><div class="swatches" style="--0:#E2E6D6;--1:#E2E6D6;--2:#E2E6D6;--3:#E2E6D6;--4:#E2E6D6"></div></td><td><div class="swatches" style="--0:#555555;--1:#555555;--2:#555555;--3:#555555;--4:#555555"></div></td></tr>
	<tr><td>ScriptOperator</td>                       <td><div class="swatches" style="--0:#7F7F00;--1:#7F7F00;--2:#7F7F00;--3:#7F7F00;--4:#7F7F00"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td></tr>
	<tr><td>ScriptNumber</td>                         <td><div class="swatches" style="--0:#007F7F;--1:#007F7F;--2:#007F7F;--3:#007F7F;--4:#007F7F"></div></td><td><div class="swatches" style="--0:#FFC600;--1:#FFC600;--2:#FFC600;--3:#FFC600;--4:#FFC600"></div></td></tr>
	<tr><td>ScriptString</td>                         <td><div class="swatches" style="--0:#7F007F;--1:#7F007F;--2:#7F007F;--3:#7F007F;--4:#7F007F"></div></td><td><div class="swatches" style="--0:#ADF195;--1:#ADF195;--2:#ADF195;--3:#ADF195;--4:#ADF195"></div></td></tr>
	<tr><td>ScriptComment</td>                        <td><div class="swatches" style="--0:#007F00;--1:#007F00;--2:#007F00;--3:#007F00;--4:#007F00"></div></td><td><div class="swatches" style="--0:#666666;--1:#666666;--2:#666666;--3:#666666;--4:#666666"></div></td></tr>
	<tr><td>ScriptPreprocessor</td>                   <td><div class="swatches" style="--0:#7F0000;--1:#7F0000;--2:#7F0000;--3:#7F0000;--4:#7F0000"></div></td><td><div class="swatches" style="--0:#66FFCC;--1:#66FFCC;--2:#66FFCC;--3:#66FFCC;--4:#66FFCC"></div></td></tr>
	<tr><td>ScriptKeyword</td>                        <td><div class="swatches" style="--0:#00007F;--1:#00007F;--2:#00007F;--3:#00007F;--4:#00007F"></div></td><td><div class="swatches" style="--0:#F86D7C;--1:#F86D7C;--2:#F86D7C;--3:#F86D7C;--4:#F86D7C"></div></td></tr>
	<tr><td>ScriptBuiltInFunction</td>                <td><div class="swatches" style="--0:#00007F;--1:#00007F;--2:#00007F;--3:#00007F;--4:#00007F"></div></td><td><div class="swatches" style="--0:#84D6F7;--1:#84D6F7;--2:#84D6F7;--3:#84D6F7;--4:#84D6F7"></div></td></tr>
	<tr><td>ScriptWarning</td>                        <td><div class="swatches" style="--0:#0000FF;--1:#0000FF;--2:#0000FF;--3:#0000FF;--4:#0000FF"></div></td><td><div class="swatches" style="--0:#FF7315;--1:#FF7315;--2:#FF7315;--3:#FF7315;--4:#FF7315"></div></td></tr>
	<tr><td>ScriptError</td>                          <td><div class="swatches" style="--0:#FF0000;--1:#FF0000;--2:#FF0000;--3:#FF0000;--4:#FF0000"></div></td><td><div class="swatches" style="--0:#FF0000;--1:#FF0000;--2:#FF0000;--3:#FF0000;--4:#FF0000"></div></td></tr>
	<tr><td>DebuggerCurrentLine</td>                  <td><div class="swatches" style="--0:#FFFFCC;--1:#FFFFCC;--2:#FFFFCC;--3:#FFFFCC;--4:#FFFFCC"></div></td><td><div class="swatches" style="--0:#2A3C4C;--1:#2A3C4C;--2:#2A3C4C;--3:#2A3C4C;--4:#2A3C4C"></div></td></tr>
	<tr><td>DebuggerErrorLine</td>                    <td><div class="swatches" style="--0:#FFCCCC;--1:#FFCCCC;--2:#FFCCCC;--3:#FFCCCC;--4:#FFCCCC"></div></td><td><div class="swatches" style="--0:#4C2A2A;--1:#4C2A2A;--2:#4C2A2A;--3:#4C2A2A;--4:#4C2A2A"></div></td></tr>
	<tr><td>DiffFilePathText</td>                     <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#AAAAAA;--4:#AAAAAA"></div></td></tr>
	<tr><td>DiffTextHunkInfo</td>                     <td><div class="swatches" style="--0:#757575;--1:#757575;--2:#757575;--3:#757575;--4:#757575"></div></td><td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#AAAAAA;--4:#AAAAAA"></div></td></tr>
	<tr><td>DiffTextNoChange</td>                     <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td></tr>
	<tr><td>DiffTextAddition</td>                     <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td></tr>
	<tr><td>DiffTextDeletion</td>                     <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#000000;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td></tr>
	<tr><td>DiffTextSeparatorBackground</td>          <td><div class="swatches" style="--0:#ECF3FF;--1:#ECF3FF;--2:#ECF3FF;--3:#ECF3FF;--4:#ECF3FF"></div></td><td><div class="swatches" style="--0:#313949;--1:#313949;--2:#313949;--3:#313949;--4:#313949"></div></td></tr>
	<tr><td>DiffTextNoChangeBackground</td>           <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#1B1F20;--1:#1B1F20;--2:#1B1F20;--3:#1B1F20;--4:#1B1F20"></div></td></tr>
	<tr><td>DiffTextAdditionBackground</td>           <td><div class="swatches" style="--0:#E1F7E8;--1:#E1F7E8;--2:#E1F7E8;--3:#E1F7E8;--4:#E1F7E8"></div></td><td><div class="swatches" style="--0:#303F2C;--1:#303F2C;--2:#303F2C;--3:#303F2C;--4:#303F2C"></div></td></tr>
	<tr><td>DiffTextDeletionBackground</td>           <td><div class="swatches" style="--0:#FFDBDB;--1:#FFDBDB;--2:#FFDBDB;--3:#FFDBDB;--4:#FFDBDB"></div></td><td><div class="swatches" style="--0:#481E18;--1:#481E18;--2:#481E18;--3:#481E18;--4:#481E18"></div></td></tr>
	<tr><td>DiffLineNum</td>                          <td><div class="swatches" style="--0:#757575;--1:#757575;--2:#757575;--3:#757575;--4:#757575"></div></td><td><div class="swatches" style="--0:#AAAAAA;--1:#AAAAAA;--2:#AAAAAA;--3:#AAAAAA;--4:#AAAAAA"></div></td></tr>
	<tr><td>DiffLineNumSeparatorBackground</td>       <td><div class="swatches" style="--0:#D8E6FF;--1:#D8E6FF;--2:#D8E6FF;--3:#D8E6FF;--4:#D8E6FF"></div></td><td><div class="swatches" style="--0:#3C537B;--1:#3C537B;--2:#3C537B;--3:#3C537B;--4:#3C537B"></div></td></tr>
	<tr><td>DiffLineNumNoChangeBackground</td>        <td><div class="swatches" style="--0:#FAFAFA;--1:#FAFAFA;--2:#FAFAFA;--3:#FAFAFA;--4:#FAFAFA"></div></td><td><div class="swatches" style="--0:#1B2023;--1:#1B2023;--2:#1B2023;--3:#1B2023;--4:#1B2023"></div></td></tr>
	<tr><td>DiffLineNumAdditionBackground</td>        <td><div class="swatches" style="--0:#CEF1D9;--1:#CEF1D9;--2:#CEF1D9;--3:#CEF1D9;--4:#CEF1D9"></div></td><td><div class="swatches" style="--0:#374D31;--1:#374D31;--2:#374D31;--3:#374D31;--4:#374D31"></div></td></tr>
	<tr><td>DiffLineNumDeletionBackground</td>        <td><div class="swatches" style="--0:#FFCACA;--1:#FFCACA;--2:#FFCACA;--3:#FFCACA;--4:#FFCACA"></div></td><td><div class="swatches" style="--0:#5B221B;--1:#5B221B;--2:#5B221B;--3:#5B221B;--4:#5B221B"></div></td></tr>
	<tr><td>DiffFilePathBackground</td>               <td><div class="swatches" style="--0:#FAFAFA;--1:#FAFAFA;--2:#FAFAFA;--3:#FAFAFA;--4:#FAFAFA"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>DiffFilePathBorder</td>                   <td><div class="swatches" style="--0:#EBEBEB;--1:#EBEBEB;--2:#EBEBEB;--3:#EBEBEB;--4:#EBEBEB"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>Separator</td>                            <td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>ButtonBorder</td>                         <td><div class="swatches" style="--0:#B6B6B6;--1:#B6B6B6;--2:#B6B6B6;--3:#CCCCCC;--4:#B6B6B6"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#353535;--3:#353535;--4:#353535"></div></td></tr>
	<tr><td>ButtonText</td>                           <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#787878;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#FFFFFF;--2:#CCCCCC;--3:#555555;--4:#CCCCCC"></div></td></tr>
	<tr><td>InputFieldBorder</td>                     <td><div class="swatches" style="--0:#C8C8C8;--1:#6692DC;--2:#C8C8C8;--3:#B6B6B6;--4:#A8A8A8"></div></td><td><div class="swatches" style="--0:#1A1A1A;--1:#35B5FF;--2:#1A1A1A;--3:#424242;--4:#3A3A3A"></div></td></tr>
	<tr><td>CheckedFieldBackground</td>               <td><div class="swatches" style="--0:#FFFFFF;--1:#00A2FF;--2:#DBDBDB;--3:#C8C8C8;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#252525;--1:#252525;--2:#252525;--3:#353535;--4:#252525"></div></td></tr>
	<tr><td>CheckedFieldBorder</td>                   <td><div class="swatches" style="--0:#B6B6B6;--1:#B6B6B6;--2:#B6B6B6;--3:#B6B6B6;--4:#A8A8A8"></div></td><td><div class="swatches" style="--0:#1A1A1A;--1:#1A1A1A;--2:#1A1A1A;--3:#404040;--4:#3A3A3A"></div></td></tr>
	<tr><td>CheckedFieldIndicator</td>                <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#888888;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#35B5FF;--1:#35B5FF;--2:#35B5FF;--3:#555555;--4:#35B5FF"></div></td></tr>
	<tr><td>HeaderSection</td>                        <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#DBDBDB;--3:#B6B6B6;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#353535;--1:#353535;--2:#292929;--3:#353535;--4:#484848"></div></td></tr>
	<tr><td>Midlight</td>                             <td><div class="swatches" style="--0:#E3E3E3;--1:#E3E3E3;--2:#E3E3E3;--3:#E3E3E3;--4:#E3E3E3"></div></td><td><div class="swatches" style="--0:#222222;--1:#222222;--2:#222222;--3:#222222;--4:#222222"></div></td></tr>
	<tr><td>StatusBar</td>                            <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#2E2E2E;--1:#2E2E2E;--2:#2E2E2E;--3:#2E2E2E;--4:#2E2E2E"></div></td></tr>
	<tr><td>DialogButton</td>                         <td><div class="swatches" style="--0:#FFFFFF;--1:#DBDBDB;--2:#DBDBDB;--3:#FFFFFF;--4:#E4EEFE"></div></td><td><div class="swatches" style="--0:#3C3C3C;--1:#333333;--2:#333333;--3:#3C3C3C;--4:#424242"></div></td></tr>
	<tr><td>DialogButtonText</td>                     <td><div class="swatches" style="--0:#000000;--1:#000000;--2:#000000;--3:#B8B8B8;--4:#000000"></div></td><td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#666666;--4:#CCCCCC"></div></td></tr>
	<tr><td>DialogButtonBorder</td>                   <td><div class="swatches" style="--0:#CCCCCC;--1:#CCCCCC;--2:#CCCCCC;--3:#CCCCCC;--4:#CCCCCC"></div></td><td><div class="swatches" style="--0:#3C3C3C;--1:#3C3C3C;--2:#3C3C3C;--3:#3C3C3C;--4:#3C3C3C"></div></td></tr>
	<tr><td>DialogMainButton</td>                     <td><div class="swatches" style="--0:#00A2FF;--1:#0074BD;--2:#0074BD;--3:#99DAFF;--4:#32B5FF"></div></td><td><div class="swatches" style="--0:#00A2FF;--1:#0074BD;--2:#0074BD;--3:#3C3C3C;--4:#32B5FF"></div></td></tr>
	<tr><td>DialogMainButtonText</td>                 <td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#FFFFFF;--4:#FFFFFF"></div></td><td><div class="swatches" style="--0:#FFFFFF;--1:#FFFFFF;--2:#FFFFFF;--3:#666666;--4:#FFFFFF"></div></td></tr>
	<tr><td>Merge3HighlightOriginal</td>              <td><div class="swatches" style="--0:#EFF5FE;--1:#EFF5FE;--2:#EFF5FE;--3:#EFF5FE;--4:#EFF5FE"></div></td><td><div class="swatches" style="--0:#2E3A4D;--1:#2E3A4D;--2:#2E3A4D;--3:#2E3A4D;--4:#2E3A4D"></div></td></tr>
	<tr><td>Merge3HighlightMine</td>                  <td><div class="swatches" style="--0:#FEFBD8;--1:#FEFBD8;--2:#FEFBD8;--3:#FEFBD8;--4:#FEFBD8"></div></td><td><div class="swatches" style="--0:#403E26;--1:#403E26;--2:#403E26;--3:#403E26;--4:#403E26"></div></td></tr>
	<tr><td>Merge3HighlightTheirs</td>                <td><div class="swatches" style="--0:#FEF2EA;--1:#FEF2EA;--2:#FEF2EA;--3:#FEF2EA;--4:#FEF2EA"></div></td><td><div class="swatches" style="--0:#4D3A2E;--1:#4D3A2E;--2:#4D3A2E;--3:#4D3A2E;--4:#4D3A2E"></div></td></tr>
	</tbody>
</table>

<!--

local theme = settings().Studio.Theme
for _, c in pairs(Enum.StudioStyleGuideColor:GetEnumItems()) do
	local s = {c.Value,c.Name}
	for _, m in pairs(Enum.StudioStyleGuideModifier:GetEnumItems()) do
		local c = theme:GetColor(c, m)
		s[#s+1] = string.format("#%02X%02X%02X",c.r*255,c.g*255,c.b*255)
	end
	print(table.concat(s, "\t"))
end

-->

# Members

## MainBackground
The background for most widgets.

## Titlebar
The title bar of panel widgets.

## Dropdown
The background of the menu component of a dropdown widget.

## Tooltip
The background of a tooltip.

## Notification
The background of a notification.

## ScrollBar
The thumb component of a scrollbar.

## ScrollBarBackground
The track component of a scrollbar.

## TabBar
The background of the tab bar that contains tab widgets.

## Tab
The background of a tab widget.

## RibbonTab
The background of a ribbon tab widget.

## RibbonTabTopBar
The bar that appears above a selected ribbon tab.

## Button
The background of a button widget.

## MainButton
## RibbonButton
The background of a button widget on the ribbon bar.

## ViewPortBackground
## InputFieldBackground
## Item
## TableItem
## CategoryItem
## GameSettingsTableItem
## GameSettingsTooltip
## EmulatorBar
## EmulatorDropDown
## ColorPickerFrame
## CurrentMarker
## Border
## Shadow
## Light
## Dark
## Mid
## MainText
## SubText
## TitlebarText
## BrightText
## DimmedText
## LinkText
Text that has a hyperlink.

## WarningText
Text in the output panel that indicates a warning.

## ErrorText
Text in the output panel that indicates an error.

## InfoText
Text in the output panel that indicates non-printed information.

## SensitiveText
Text in the output panel that indicates sensitive information.

## ScriptSideWidget

## ScriptBackground
Background in the script editor.

## ScriptText
Detault text in the script editor.

## ScriptSelectionText
Selected text in the script editor.

## ScriptSelectionBackground
Background of selected text in the script editor.

## ScriptFindSelectionBackground
Background of searched text in the script editor.

## ScriptMatchingWordSelectionBackground
Background of words matching selected text in the script editor.

## ScriptOperator
Lua operators in the script editor.

## ScriptNumber
Lua numbers in the script editor.

## ScriptString
Lua strings in the script editor.

## ScriptComment
Lua comments in the script editor.

## ScriptPreprocessor
Lua preprocessors in the script editor.

## ScriptKeyword
Lua keywords in the script editor.

## ScriptBuiltInFunction
Lua built-in functions in the script editor.

## ScriptWarning
Warning decoration in the script editor.

## ScriptError
Error decoration in the script editor.

## DebuggerCurrentLine
Background of current debugging line in the script editor.

## DebuggerErrorLine
Background of debugging error in the script editor.

## DiffFilePathText
## DiffTextHunkInfo
## DiffTextNoChange
## DiffTextAddition
## DiffTextDeletion
## DiffTextSeparatorBackground
## DiffTextNoChangeBackground
## DiffTextAdditionBackground
## DiffTextDeletionBackground
## DiffLineNum
## DiffLineNumSeparatorBackground
## DiffLineNumNoChangeBackground
## DiffLineNumAdditionBackground
## DiffLineNumDeletionBackground
## DiffFilePathBackground
## DiffFilePathBorder
## Separator
## ButtonBorder
## ButtonText
## InputFieldBorder
## CheckedFieldBackground
## CheckedFieldBorder
## CheckedFieldIndicator
## HeaderSection
## Midlight
## StatusBar
## DialogButton
## DialogButtonText
## DialogButtonBorder
## DialogMainButton
## DialogMainButtonText
## Merge3HighlightOriginal
## Merge3HighlightMine
## Merge3HighlightTheirs
