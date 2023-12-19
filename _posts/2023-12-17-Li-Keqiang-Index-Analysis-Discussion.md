---
layout: post
title:  "Testing the Li Keqiang Index: Analysis and Discussion"
author: William Martindale
description: The results of my Li Keqiang Index project.
image: /assets/images/blog-image.jpg
---
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>project_analysis</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0px solid transparent;
  border-right: 0px solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0px solid transparent;
  border-bottom: 0px solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
	border:1px solid transparent;
  background-color: transparent;
  position: absolute;
	z-index:1;
	right:3%;
	top: 0;
	bottom: 0;
	margin: auto;
	padding: 7px 0;
	display: none;
	vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
	content: "X";
	display: block;
	width: 15px;
	height: 15px;
	text-align: center;
	color:#000;
	font-weight: normal;
	font-size: 12px;
	cursor: pointer;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
  background: inherit;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-bottom:10px;
  margin-top:0; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  font-size:36px;
  line-height:40px; }

h2.bp3-heading, .bp3-running-text h2{
  font-size:28px;
  line-height:32px; }

h3.bp3-heading, .bp3-running-text h3{
  font-size:22px;
  line-height:25px; }

h4.bp3-heading, .bp3-running-text h4{
  font-size:18px;
  line-height:21px; }

h5.bp3-heading, .bp3-running-text h5{
  font-size:16px;
  line-height:19px; }

h6.bp3-heading, .bp3-running-text h6{
  font-size:14px;
  line-height:16px; }
.bp3-ui-text{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none; }

.bp3-monospace-text{
  font-family:monospace;
  text-transform:none; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  font-size:14px;
  line-height:1.5; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15);
    margin:20px 0; }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  color:#106ba3;
  text-decoration:none; }
  a:hover{
    color:#106ba3;
    cursor:pointer;
    text-decoration:underline; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  font-size:smaller;
  padding:2px 5px; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  color:#182026;
  display:block;
  font-size:13px;
  line-height:1.4;
  margin:10px 0;
  padding:13px 15px 12px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit;
    font-size:inherit;
    padding:0; }

.bp3-running-text kbd, .bp3-key{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-family:inherit;
  font-size:12px;
  height:24px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  line-height:24px;
  min-width:24px;
  padding:3px 6px;
  vertical-align:middle; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  margin:0 0 10px;
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  list-style:none;
  margin:0;
  padding:0; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    font-size:40px;
    margin-right:20px;
    margin-top:0; }

.bp3-alert-contents{
  word-break:break-word; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  cursor:default;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  height:30px;
  list-style:none;
  margin:0;
  padding:0; }
  .bp3-breadcrumbs > li{
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }
    .bp3-breadcrumbs > li::after{
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 00-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 001.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      content:"";
      display:block;
      height:16px;
      margin:0 5px;
      width:16px; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    font-size:inherit;
    font-weight:inherit;
    vertical-align:baseline; }

.bp3-breadcrumbs-collapsed{
  background:#ced9e0;
  border:none;
  border-radius:3px;
  cursor:pointer;
  margin-right:2px;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    content:"";
    display:block;
    height:16px;
    width:16px; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    color:#182026;
    text-decoration:none; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  min-height:30px;
  min-width:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      background-color:#106ba3;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      background-color:#0e5a8a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      background-color:#0d8050;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      background-color:#0a6640;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      background-color:#bf7326;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      background-color:#a66321;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      background-color:#c23030;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      background-color:#a82a2a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-height:40px;
    min-width:40px;
    font-size:16px;
    padding:5px 15px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-height:24px;
    min-width:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      margin:0;
      position:absolute; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button.bp3-minimal:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button.bp3-outlined{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    border:1px solid rgba(24, 32, 38, 0.2);
    -webkit-box-sizing:border-box;
            box-sizing:border-box; }
    .bp3-button.bp3-outlined:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-outlined:active, .bp3-button.bp3-outlined.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-outlined{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-outlined:hover, .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-outlined:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover, .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover, .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover, .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover, .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled:hover{
      border-color:rgba(92, 112, 128, 0.1); }
    .bp3-dark .bp3-button.bp3-outlined{
      border-color:rgba(255, 255, 255, 0.4); }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        border-color:rgba(255, 255, 255, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      border-color:rgba(16, 107, 163, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        border-color:rgba(16, 107, 163, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        border-color:rgba(72, 175, 240, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          border-color:rgba(72, 175, 240, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      border-color:rgba(13, 128, 80, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        border-color:rgba(13, 128, 80, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        border-color:rgba(61, 204, 145, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          border-color:rgba(61, 204, 145, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      border-color:rgba(191, 115, 38, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        border-color:rgba(191, 115, 38, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        border-color:rgba(255, 179, 102, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          border-color:rgba(255, 179, 102, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      border-color:rgba(194, 48, 48, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        border-color:rgba(194, 48, 48, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        border-color:rgba(255, 115, 115, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          border-color:rgba(255, 115, 115, 0.2); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    border-bottom-right-radius:0;
    border-top-right-radius:0;
    margin-right:-1px; }
  .bp3-button-group.bp3-minimal .bp3-button{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      height:100%;
      width:unset; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  font-size:14px;
  line-height:1.5;
  background-color:rgba(138, 155, 168, 0.15);
  border-radius:3px;
  padding:10px 12px 9px;
  position:relative;
  width:100%; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout .bp3-heading{
    line-height:20px;
    margin-bottom:5px;
    margin-top:0; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  opacity:0.9;
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  width:100%; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }

.bp3-dialog{
  background:#ebf1f5;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text;
  width:500px; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    background:#293742;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-dialog-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding-left:20px;
  padding-right:5px;
  z-index:30; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    background:#30404d;
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  line-height:18px;
  margin:20px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-multistep-dialog-panels{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }

.bp3-multistep-dialog-left-panel{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column; }
  .bp3-dark .bp3-multistep-dialog-left-panel{
    background:#202b33; }

.bp3-multistep-dialog-right-panel{
  background-color:#f5f8fa;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  border-radius:0 0 6px 0;
  -webkit-box-flex:3;
      -ms-flex:3;
          flex:3;
  min-width:0; }
  .bp3-dark .bp3-multistep-dialog-right-panel{
    background-color:#293742;
    border-left:1px solid rgba(16, 22, 26, 0.4); }

.bp3-multistep-dialog-footer{
  background-color:#ffffff;
  border-radius:0 0 6px 0;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  padding:10px; }
  .bp3-dark .bp3-multistep-dialog-footer{
    background:#30404d;
    border-top:1px solid rgba(16, 22, 26, 0.4); }

.bp3-dialog-step-container{
  background-color:#f5f8fa;
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-dialog-step-container{
    background:#293742;
    border-bottom:1px solid rgba(16, 22, 26, 0.4); }
  .bp3-dialog-step-container.bp3-dialog-step-viewed{
    background-color:#ffffff; }
    .bp3-dark .bp3-dialog-step-container.bp3-dialog-step-viewed{
      background:#30404d; }

.bp3-dialog-step{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:#f5f8fa;
  border-radius:6px;
  cursor:not-allowed;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:4px;
  padding:6px 14px; }
  .bp3-dark .bp3-dialog-step{
    background:#293742; }
  .bp3-dialog-step-viewed .bp3-dialog-step{
    background-color:#ffffff;
    cursor:pointer; }
    .bp3-dark .bp3-dialog-step-viewed .bp3-dialog-step{
      background:#30404d; }
  .bp3-dialog-step:hover{
    background-color:#f5f8fa; }
    .bp3-dark .bp3-dialog-step:hover{
      background:#293742; }

.bp3-dialog-step-icon{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:rgba(92, 112, 128, 0.6);
  border-radius:50%;
  color:#ffffff;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:25px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:25px; }
  .bp3-dark .bp3-dialog-step-icon{
    background-color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#2b95d6; }
  .bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#8a9ba8; }

.bp3-dialog-step-title{
  color:rgba(92, 112, 128, 0.6);
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  padding-left:10px; }
  .bp3-dark .bp3-dialog-step-title{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-title{
    color:#2b95d6; }
  .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
    color:#182026; }
    .bp3-dark .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
      color:#f5f8fa; }
.bp3-drawer{
  background:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    height:50%;
    left:0;
    right:0;
    top:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-bottom{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-left{
    bottom:0;
    left:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-right{
    bottom:0;
    right:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    bottom:0;
    right:0;
    top:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    background:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-drawer-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding:5px;
  padding-left:20px;
  position:relative; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  line-height:18px;
  overflow:auto; }

.bp3-drawer-footer{
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  padding:10px 20px;
  position:relative; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  cursor:text;
  display:inline-block;
  max-width:100%;
  position:relative;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    bottom:-3px;
    left:-3px;
    position:absolute;
    right:-3px;
    top:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  color:inherit;
  display:inherit;
  font:inherit;
  letter-spacing:inherit;
  max-width:inherit;
  min-width:inherit;
  position:relative;
  resize:none;
  text-transform:inherit;
  vertical-align:top; }

.bp3-editable-text-input{
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0;
  white-space:pre-wrap;
  width:100%; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    left:0;
    position:absolute;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-divider{
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    border-radius:inherit;
    z-index:2; }
    .bp3-control-group .bp3-input:focus{
      border-radius:3px;
      z-index:14; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    border-radius:inherit;
    z-index:4; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-left-container,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group .bp3-select:focus-within{
    z-index:5; }
  .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:-1px; }
  .bp3-control-group:not(.bp3-vertical) > .bp3-divider:not(:first-child){
    margin-left:6px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    border-radius:0 3px 3px 0;
    margin-right:0; }
  .bp3-control-group > :only-child{
    border-radius:3px;
    margin-right:0; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group .bp3-numeric-input:not(:first-child) .bp3-input-group{
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-control-group.bp3-fill{
    width:100%; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      border-radius:3px 3px 0 0;
      margin-top:0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  cursor:pointer;
  display:block;
  margin-bottom:10px;
  position:relative;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    left:0;
    opacity:0;
    position:absolute;
    top:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    cursor:pointer;
    display:inline-block;
    font-size:16px;
    height:1em;
    margin-right:10px;
    margin-top:-3px;
    position:relative;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none;
    vertical-align:middle;
    width:1em; }
    .bp3-control .bp3-control-indicator::before{
      content:"";
      display:block;
      height:1em;
      width:1em; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    background:#d8e1e8;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-left:10px;
    margin-top:1px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 00-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0012 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:auto; }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      background:#ffffff;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      height:calc(1em - 4px);
      left:0;
      margin:2px;
      position:absolute;
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      width:calc(1em - 4px); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    font-size:0.7em;
    text-align:center; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    line-height:0;
    margin-left:0.5em;
    margin-right:1.2em;
    visibility:hidden; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    line-height:1em;
    margin-left:1.2em;
    margin-right:0.5em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    line-height:1em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    line-height:0;
    visibility:hidden; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      background:#202b33;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  cursor:pointer;
  display:inline-block;
  height:30px;
  position:relative; }
  .bp3-file-input input{
    margin:0;
    min-width:200px;
    opacity:0; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      background:rgba(206, 217, 224, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(92, 112, 128, 0.6);
        cursor:not-allowed;
        outline:none; }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        background:rgba(57, 75, 89, 0.5);
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          -webkit-box-shadow:none;
                  box-shadow:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:rgba(92, 112, 128, 0.6);
  left:0;
  padding-right:80px;
  position:absolute;
  right:0;
  top:0;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-file-upload-input::after{
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026;
    min-height:24px;
    min-width:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    border-radius:3px;
    content:"Browse";
    line-height:24px;
    margin:3px;
    position:absolute;
    right:0;
    text-align:center;
    top:0;
    width:70px; }
    .bp3-file-upload-input::after:hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-file-upload-input:active::after{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-large .bp3-file-upload-input{
    font-size:16px;
    height:40px;
    line-height:40px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-height:30px;
      min-width:30px;
      line-height:30px;
      margin:5px;
      width:85px; }
  .bp3-dark .bp3-file-upload-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        background-color:#30404d;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        background-color:#202b33;
        background-image:none;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:active::after{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    color:#5c7080;
    font-size:12px;
    margin-top:5px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      line-height:40px;
      margin:0 10px 0 0; }
    .bp3-form-group.bp3-inline label.bp3-label{
      line-height:30px;
      margin:0 10px 0 0; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-input-left-container:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-input-left-container:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-height:24px;
    min-width:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-icon{
    z-index:1; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group > .bp3-icon{
    color:#5c7080; }
    .bp3-input-group > .bp3-input-left-container > .bp3-icon:empty,
    .bp3-input-group > .bp3-icon:empty{
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-height:30px;
    min-width:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle; }
  .bp3-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-input.bp3-large{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-bottom:15px;
  margin-top:0; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    font-weight:400;
    vertical-align:top;
    width:100%; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  min-height:0;
  padding:0;
  width:30px; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  -moz-appearance:none;
  -webkit-appearance:none;
  border-radius:3px;
  height:30px;
  padding:0 25px 0 10px;
  width:100%; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  background:none;
  -webkit-box-shadow:none;
          box-shadow:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    background:rgba(167, 182, 194, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026;
    text-decoration:none; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    background:rgba(115, 134, 148, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      color:rgba(167, 182, 194, 0.6);
      cursor:not-allowed; }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  font-size:16px;
  height:40px;
  padding-right:35px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    background-color:#202b33;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  background-color:rgba(206, 217, 224, 0.5);
  -webkit-box-shadow:none;
          box-shadow:none;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  color:#5c7080;
  pointer-events:none;
  position:absolute;
  right:7px;
  top:7px; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  letter-spacing:normal;
  position:relative;
  vertical-align:middle; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    right:12px;
    top:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select option:disabled, .bp3-dark
  .bp3-select option:disabled{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    text-align:left;
    vertical-align:top; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td,
  .bp3-running-text table tfoot tr:first-child th,
  table.bp3-html-table tfoot tr:first-child th,
  .bp3-running-text table tfoot tr:first-child td,
  table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td,
  .bp3-dark .bp3-running-text table tfoot tr:first-child th,
  .bp3-running-text .bp3-dark table tfoot tr:first-child th,
  .bp3-dark table.bp3-html-table tfoot tr:first-child th,
  .bp3-dark .bp3-running-text table tfoot tr:first-child td,
  .bp3-running-text .bp3-dark table tfoot tr:first-child td,
  .bp3-dark table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-bottom:6px;
  padding-top:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td,
table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
  table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table{ }
  .bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
    background:rgba(92, 112, 128, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td,
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
      -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
              box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
    -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
    background-color:rgba(92, 112, 128, 0.3);
    cursor:pointer; }
  .bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
    background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  padding-bottom:0;
  top:40px; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-left:0;
  margin-right:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  font-family:"Icons20";
  font-size:inherit;
  font-style:normal;
  font-weight:400;
  line-height:1; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagnosis::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-lab-test::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }
  .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{ }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  background:#ffffff;
  border-radius:3px;
  color:#182026;
  list-style:none;
  margin:0;
  min-width:180px;
  padding:5px;
  text-align:left; }

.bp3-menu-divider{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px; }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  color:inherit;
  line-height:20px;
  padding:5px 7px;
  text-decoration:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    color:#5c7080;
    margin-top:2px; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit !important;
    color:rgba(92, 112, 128, 0.6) !important;
    cursor:not-allowed !important;
    outline:none !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    font-size:16px;
    line-height:22px;
    padding:9px 7px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-right:10px;
      margin-top:1px; }

button.bp3-menu-item{
  background:none;
  border:none;
  text-align:left;
  width:100%; }
.bp3-menu-header{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px;
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    line-height:17px;
    margin:0;
    padding:10px 7px 0 1px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    font-size:18px;
    padding-bottom:5px;
    padding-top:15px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item{ }
  .bp3-dark .bp3-menu-item.bp3-intent-primary{
    color:#48aff0; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#48aff0; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-success{
    color:#3dcc91; }
    .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#3dcc91; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning{
    color:#ffb366; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#ffb366; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger{
    color:#ff7373; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#ff7373; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item::before,
  .bp3-dark .bp3-menu-item > .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-menu-item .bp3-menu-item-label{
    color:#a7b6c2; }
  .bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
    background-color:rgba(138, 155, 168, 0.3); }
  .bp3-dark .bp3-menu-item.bp3-disabled{
    color:rgba(167, 182, 194, 0.6) !important; }
    .bp3-dark .bp3-menu-item.bp3-disabled::before,
    .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  background-color:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  height:50px;
  padding:0 15px;
  position:relative;
  width:100%;
  z-index:10; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    left:0;
    position:fixed;
    right:0;
    top:0; }

.bp3-navbar-heading{
  font-size:16px;
  margin-right:15px; }

.bp3-navbar-group{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px;
  margin:0 10px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:100%;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  text-align:center;
  width:100%; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  bottom:0;
  left:0;
  position:static;
  right:0;
  top:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    overflow:hidden;
    position:fixed; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    overflow:auto;
    position:fixed; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  bottom:0;
  left:0;
  position:fixed;
  right:0;
  top:0;
  opacity:1;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  z-index:20; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }
  .bp3-panel-stack-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-panel-stack2{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack2-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack2-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack2-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack2-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack2-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack2-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-view{
    background-color:#30404d; }
  .bp3-panel-stack2-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter, .bp3-panel-stack2-push .bp3-panel-stack2-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter-active, .bp3-panel-stack2-push .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter, .bp3-panel-stack2-pop .bp3-panel-stack2-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter-active, .bp3-panel-stack2-pop .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  border-radius:3px;
  display:inline-block;
  z-index:20; }
  .bp3-popover .bp3-popover-arrow{
    height:30px;
    position:absolute;
    width:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      height:20px;
      margin:5px;
      width:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-bottom:17px;
    margin-top:-17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-left:-17px;
    margin-right:17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover .bp3-popover-content{
    border-radius:3px;
    position:relative; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  border-radius:2px;
  content:"";
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg); }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  left:0;
  position:absolute;
  right:0;
  top:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  background:rgba(92, 112, 128, 0.2);
  border-radius:40px;
  display:block;
  height:8px;
  overflow:hidden;
  position:relative;
  width:100%; }
  .bp3-progress-bar .bp3-progress-meter{
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    border-radius:40px;
    height:100%;
    position:absolute;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:100%; }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  color:transparent !important;
  cursor:default;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  height:40px;
  min-width:150px;
  width:100%;
  cursor:default;
  outline:none;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    cursor:not-allowed;
    opacity:0.5; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  height:6px;
  left:0;
  right:0;
  top:5px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  height:16px;
  left:0;
  position:absolute;
  top:0;
  width:16px; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab;
    z-index:2; }
  .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    background:#bfccd6;
    -webkit-box-shadow:none;
            box-shadow:none;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    background:#5c7080;
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-slider-handle .bp3-slider-label{
    background:#394b59;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    color:#f5f8fa;
    margin-left:8px; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      background:#e1e8ed;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-bottom-right-radius:0;
    border-top-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    border-bottom-left-radius:0;
    border-top-left-radius:0;
    margin-left:8px; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  font-size:12px;
  line-height:1;
  padding:2px 5px;
  position:absolute;
  vertical-align:top; }

.bp3-slider.bp3-vertical{
  height:150px;
  min-width:40px;
  width:40px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    bottom:0;
    height:auto;
    left:5px;
    top:0;
    width:6px; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-left:0;
      margin-top:-8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      height:8px;
      margin-left:0;
      width:16px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-bottom-right-radius:3px;
      border-top-left-radius:0; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      border-bottom-left-radius:0;
      border-bottom-right-radius:0;
      border-top-left-radius:3px;
      margin-bottom:8px; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round;
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      padding:0 10px;
      width:100%; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        background-color:rgba(19, 124, 189, 0.2);
        -webkit-box-shadow:none;
                box-shadow:none; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      background-color:rgba(19, 124, 189, 0.2);
      border-radius:3px;
      bottom:0;
      height:auto;
      left:0;
      right:0;
      top:0; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  border:none;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  list-style:none;
  margin:0;
  padding:0;
  position:relative; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:#182026;
  cursor:pointer;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  font-size:14px;
  line-height:30px;
  max-width:100%;
  position:relative;
  vertical-align:top; }
  .bp3-tab a{
    color:inherit;
    display:block;
    text-decoration:none; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    background-color:transparent !important;
    -webkit-box-shadow:none !important;
            box-shadow:none !important; }
  .bp3-tab[aria-disabled="true"]{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    font-size:16px;
    line-height:40px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  left:0;
  pointer-events:none;
  position:absolute;
  top:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    background-color:#106ba3;
    bottom:0;
    height:3px;
    left:0;
    position:absolute;
    right:0; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:#5c7080;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  color:#f5f8fa;
  font-size:12px;
  line-height:16px;
  max-width:100%;
  min-height:20px;
  min-width:20px;
  padding:2px 6px;
  position:relative; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-left:8px;
    padding-right:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    font-size:14px;
    line-height:20px;
    min-height:30px;
    min-width:30px;
    padding:5px 10px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-left:12px;
      padding-right:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  background:none;
  border:none;
  color:inherit;
  cursor:pointer;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin-bottom:-2px;
  margin-right:-6px !important;
  margin-top:-2px;
  opacity:0.5;
  padding:2px;
  padding-left:0; }
  .bp3-tag-remove:hover{
    background:none;
    opacity:0.8;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:0 5px 0 0; }
    .bp3-large .bp3-tag-remove:empty::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  line-height:inherit;
  min-height:30px;
  padding-left:5px;
  padding-right:0; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    color:#5c7080;
    margin-left:2px;
    margin-right:7px;
    margin-top:7px; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    margin-right:7px;
    margin-top:5px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:20px;
    width:80px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-height:24px;
    min-width:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-left:5px;
      margin-top:10px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-height:30px;
      min-width:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:20px 0 0;
  max-width:500px;
  min-width:300px;
  pointer-events:all;
  position:relative !important; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-delay:50ms;
            transition-delay:50ms;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    color:#5c7080;
    margin:12px;
    margin-right:0; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    background-color:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  left:0;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none;
  right:0;
  z-index:40; }
  .bp3-toast-container.bp3-toast-container-in-portal{
    position:fixed; }
  .bp3-toast-container.bp3-toast-container-inline{
    position:absolute; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0; }
  .bp3-toast-container.bp3-toast-container-bottom{
    bottom:0;
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-exit-active ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    height:22px;
    position:absolute;
    width:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      height:14px;
      margin:4px;
      width:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-bottom:11px;
    margin-top:-11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-left:-11px;
    margin-right:11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  list-style:none;
  margin:0;
  padding-left:0; }

.bp3-tree-root{
  background-color:transparent;
  cursor:default;
  padding-left:0;
  position:relative; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:30px;
  padding-right:5px;
  width:100%; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  cursor:pointer;
  padding:7px;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  margin-right:7px;
  position:relative; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  left:calc(50% - 250px);
  top:20vh;
  width:500px;
  z-index:21; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar .bp3-input{
    background-color:transparent;
    border-radius:0; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    background-color:transparent;
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MC45NzggNTAuOTc4IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA1MC45NzggNTAuOTc4OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+Cgk8Zz4KCQk8cGF0aCBzdHlsZT0iZmlsbDojMDEwMDAyOyIgZD0iTTQzLjUyLDcuNDU4QzM4LjcxMSwyLjY0OCwzMi4zMDcsMCwyNS40ODksMEMxOC42NywwLDEyLjI2NiwyLjY0OCw3LjQ1OCw3LjQ1OAoJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDAKCQkJYzYuODE2LDAsMTMuMjIxLTIuNjQ4LDE4LjAyOS03LjQ1OGM0LjgwOS00LjgwOSw3LjQ1Ny0xMS4yMTIsNy40NTctMTguMDNDNTAuOTc3LDE4LjY3LDQ4LjMyOCwxMi4yNjYsNDMuNTIsNy40NTh6CgkJCSBNNDIuMTA2LDQyLjEwNWMtNC40MzIsNC40MzEtMTAuMzMyLDYuODcyLTE2LjYxNSw2Ljg3MmgtMC4wMDJjLTYuMjg1LTAuMDAxLTEyLjE4Ny0yLjQ0MS0xNi42MTctNi44NzIKCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzIKCQkJYzQuNDMxLDQuNDMxLDYuODcxLDEwLjMzMiw2Ljg3MSwxNi42MTdDNDguOTc3LDMxLjc3Miw0Ni41MzYsMzcuNjc1LDQyLjEwNiw0Mi4xMDV6Ii8+CgkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik0yMy41NzgsMzIuMjE4Yy0wLjAyMy0xLjczNCwwLjE0My0zLjA1OSwwLjQ5Ni0zLjk3MmMwLjM1My0wLjkxMywxLjExLTEuOTk3LDIuMjcyLTMuMjUzCgkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUKCQkJYzAtMS4wOTYtMC4yNi0yLjA4OC0wLjc3OS0yLjk3OWMtMC41NjUtMC44NzktMS41MDEtMS4zMzYtMi44MDYtMS4zNjljLTEuODAyLDAuMDU3LTIuOTg1LDAuNjY3LTMuNTUsMS44MzIKCQkJYy0wLjMwMSwwLjUzNS0wLjUwMywxLjE0MS0wLjYwNywxLjgxNGMtMC4xMzksMC43MDctMC4yMDcsMS40MzItMC4yMDcsMi4xNzRoLTIuOTM3Yy0wLjA5MS0yLjIwOCwwLjQwNy00LjExNCwxLjQ5My01LjcxOQoJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQoJCQljMCwxLjE0Mi0wLjEzNywyLjExMS0wLjQxLDIuOTExYy0wLjMwOSwwLjg0NS0wLjczMSwxLjU5My0xLjI2OCwyLjI0M2MtMC40OTIsMC42NS0xLjA2OCwxLjMxOC0xLjczLDIuMDAyCgkJCWMtMC42NSwwLjY5Ny0xLjMxMywxLjQ3OS0xLjk4NywyLjM0NmMtMC4yMzksMC4zNzctMC40MjksMC43NzctMC41NjUsMS4xOTljLTAuMTYsMC45NTktMC4yMTcsMS45NTEtMC4xNzEsMi45NzkKCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4=);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}
.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}
.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}
.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-border-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0px;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-warn-color0);
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px 5px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
  resize: both;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FileDialog-Checkbox {
  margin-top: 35px;
  display: flex;
  flex-direction: row;
  align-items: end;
  width: 100%;
}

.jp-FileDialog-Checkbox > label {
  flex: 1 1 auto;
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
  overflow-x: auto;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 50px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -50px; margin-right: -50px;
  padding-bottom: 50px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 50px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
  outline: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -50px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .remote-caret {
  position: relative;
  border-left: 2px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .remote-caret > div {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -2px;
  font-size: 0.95em;
  background-color: rgb(250, 129, 0);
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 3;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .remote-caret.hide-name > div {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .remote-caret:hover > div {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
  margin: 8px 12px 0px 12px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: flex-start;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0px;
  padding-right: 2px;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 40px;
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent {
  width: 72px;
  background: var(--jp-brand-color1);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent:focus-visible {
  background-color: var(--jp-brand-color0);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent
  .jp-icon3 {
  fill: white;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileBrowser-filterBox {
  padding: 0px;
  flex: 0 0 auto;
  margin: 8px 12px 0px 12px;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing:focus-visible {
  border: 1px solid var(--jp-brand-color1);
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon:before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

body[data-format='mobile'] .jp-OutputArea-child {
  flex-direction: column;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body[data-format='mobile'] .jp-OutputPrompt {
  flex: 0 0 auto;
  text-align: left;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  margin-left: var(--jp-notebook-padding);
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
  overflow: hidden;
}

body[data-format='mobile'] .jp-InputArea {
  flex-direction: column;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
  overflow: hidden;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

body[data-format='mobile'] .jp-InputArea-editor {
  margin-left: var(--jp-notebook-padding);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body[data-format='mobile'] .jp-InputPrompt {
  flex: 0 0 auto;
  text-align: left;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

.jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
}

.jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-collapseHeadingButton {
  display: none;
}

.jp-MarkdownCell:hover .jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook-render * {
  contain: none !important;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
  float: left;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt:before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body div {
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

.highlight  {
  margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.CodeMirror pre {
  margin: 0;
  padding: 0;
}

/* Using table instead of flexbox so that we can use break-inside property */
/* CSS rules under this comment should not be required anymore after we move to the JupyterLab 4.0 CSS */


.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  min-width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-OutputArea-child {
  display: table;
  width: 100%;
}

.jp-OutputPrompt {
  display: table-cell;
  vertical-align: top;
  min-width: var(--jp-cell-prompt-width);
}

body[data-format='mobile'] .jp-OutputPrompt {
  display: table-row;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
}

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  display: table-row;
}

.jp-OutputArea-output.jp-OutputArea-executeResult {
  width: 100%;
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }

  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}
</style>

<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: {
                    automatic: true
                    }
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="To-Recap">To Recap<a class="anchor-link" href="#To-Recap">&#182;</a></h1><p><a href="https://wijama.org/2023/12/15/Li-Keqiang-Index-Introduction-and-EDA.html">The previous blog post</a> introduced the project and performed an EDA on data related to the Li Keqiang index which raised some important concerns. Because of our EDA, we chose to perform our analysis using the logged forms of our main variables of interest: GDP, rail cargo volume, and electricity consumption. (Bank loan volume had been omitted from the analysis because no reliable data exists.) We also noticed that there was autocorrelation within countries, which would have to be dealt with. Finally, we noticed problems with our data set in general, which will be discussed at the end of this analysis.</p>
<h1 id="Model-Building">Model Building<a class="anchor-link" href="#Model-Building">&#182;</a></h1><p>The goal of this analysis was to see if rail cargo volume and electricity consumption are good estimators of GDP. I also wanted to see if this would be impacted by economic variables such as the percentage of the population in urban areas and the percentage of the economy made up of the service sector. Additionally, I wanted to see if this would be impacted by the strength of democracy in the country of interest. I expected countries with lower levels of democracy to be more likely to overreport their GDP.
To this end, I built two models: one with just the variables of interest and one that included interactions between my control variables and the economic indicators. Using the statsmodels formula API, the first model is:</p>

<pre><code>log_GDP ~ log_energy_cons+log_rail_cargo</code></pre>
<p>And the second model is:</p>

<pre><code>log_GDP ~ (log_energy_cons+log_rail_cargo)*(urban_per+service_per+democracy)-(urban_per+service_per+democracy)</code></pre>
<p><code>urban_per</code>, <code>service_per</code> and <code>democracy</code> are removed from the model because I am only interested in how they change the effect of the two economic indicators.</p>
<h1 id="Model-Fitting">Model Fitting<a class="anchor-link" href="#Model-Fitting">&#182;</a></h1><p>Before we begin, you can follow along by downloading the code for this part of the project <a href="https://github.com/WiJaMa/stat386-project/blob/main/project_analysis.ipynb">here</a>.</p>
<h3 id="Preparing-Data-and-Packages">Preparing Data and Packages<a class="anchor-link" href="#Preparing-Data-and-Packages">&#182;</a></h3><p>First, I imported the packages we'll need for the analysis:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">math</span>

<span class="kn">import</span> <span class="nn">statsmodels.api</span> <span class="k">as</span> <span class="nn">sm</span>
<span class="kn">import</span> <span class="nn">statsmodels.formula.api</span> <span class="k">as</span> <span class="nn">smf</span>
<span class="kn">from</span> <span class="nn">statsmodels.compat</span> <span class="kn">import</span> <span class="n">lzip</span>
<span class="kn">import</span> <span class="nn">statsmodels.stats.api</span> <span class="k">as</span> <span class="nn">sms</span>

<span class="kn">from</span> <span class="nn">statsmodels.stats.diagnostic</span> <span class="kn">import</span> <span class="n">het_breuschpagan</span>

<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Then, I imported the data we produced in the previous blog post:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">'keqiang.csv'</span><span class="p">)</span>
<span class="c1"># Some of our names kinda suck so let's fix them</span>
<span class="n">df</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">'Democracy Index'</span><span class="p">:</span> <span class="s1">'democracy'</span><span class="p">},</span><span class="n">inplace</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
<span class="c1"># this makes all of our quantitative vars lowercase, our qualitative ones capitalized, and y var in ALL CAPS</span>

<span class="c1"># as mentioned in EDA post, we also need to logarithm energy_cons, rail_cargo, and GDP.</span>
<span class="n">df</span><span class="p">[</span><span class="s1">'GDP'</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="n">math</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="n">item</span><span class="p">)</span> <span class="k">for</span> <span class="n">item</span> <span class="ow">in</span> <span class="n">df</span><span class="p">[</span><span class="s1">'GDP'</span><span class="p">]]</span>
<span class="n">df</span><span class="p">[</span><span class="s1">'rail_cargo'</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="n">math</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="n">item</span><span class="p">)</span> <span class="k">for</span> <span class="n">item</span> <span class="ow">in</span> <span class="n">df</span><span class="p">[</span><span class="s1">'rail_cargo'</span><span class="p">]]</span>
<span class="n">df</span><span class="p">[</span><span class="s1">'energy_cons'</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="n">math</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="n">item</span><span class="p">)</span> <span class="k">for</span> <span class="n">item</span> <span class="ow">in</span> <span class="n">df</span><span class="p">[</span><span class="s1">'energy_cons'</span><span class="p">]]</span>
<span class="n">df</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">'energy_cons'</span><span class="p">:</span> <span class="s1">'log_energy_cons'</span><span class="p">,</span>
                   <span class="s1">'rail_cargo'</span><span class="p">:</span> <span class="s1">'log_rail_cargo'</span><span class="p">,</span>
                   <span class="s1">'GDP'</span><span class="p">:</span> <span class="s1">'log_GDP'</span><span class="p">},</span><span class="n">inplace</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[2]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Year</th>
      <th>Region</th>
      <th>democracy</th>
      <th>log_energy_cons</th>
      <th>log_rail_cargo</th>
      <th>urban_per</th>
      <th>service_per</th>
      <th>log_GDP</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Canada</td>
      <td>2019</td>
      <td>North America</td>
      <td>9.22</td>
      <td>6.304906</td>
      <td>13.008256</td>
      <td>81.482</td>
      <td>67.671163</td>
      <td>28.187045</td>
    </tr>
    <tr>
      <th>1</th>
      <td>United States</td>
      <td>2019</td>
      <td>North America</td>
      <td>7.96</td>
      <td>8.291391</td>
      <td>14.672950</td>
      <td>82.459</td>
      <td>77.181114</td>
      <td>30.693523</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Austria</td>
      <td>2019</td>
      <td>Western Europe</td>
      <td>8.29</td>
      <td>4.228670</td>
      <td>9.986725</td>
      <td>58.515</td>
      <td>63.129879</td>
      <td>26.820488</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Finland</td>
      <td>2019</td>
      <td>Western Europe</td>
      <td>9.25</td>
      <td>4.431378</td>
      <td>9.236982</td>
      <td>85.446</td>
      <td>60.194782</td>
      <td>26.316172</td>
    </tr>
    <tr>
      <th>4</th>
      <td>France</td>
      <td>2019</td>
      <td>Western Europe</td>
      <td>8.12</td>
      <td>6.104842</td>
      <td>10.430967</td>
      <td>80.709</td>
      <td>70.043587</td>
      <td>28.634909</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Ordinary-Least-Squares">Ordinary Least Squares<a class="anchor-link" href="#Ordinary-Least-Squares">&#182;</a></h3><p>First, I wanted to try an ordinary least squares model to see if there was anything I needed to fix. I started with a model that just looks at the variables of interest:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#fit regression model</span>
<span class="n">fit</span> <span class="o">=</span> <span class="n">smf</span><span class="o">.</span><span class="n">ols</span><span class="p">(</span><span class="s1">'log_GDP ~ log_energy_cons+log_rail_cargo'</span><span class="p">,</span> <span class="n">data</span><span class="o">=</span><span class="n">df</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">()</span>

<span class="c1">#view model summary</span>
<span class="nb">print</span><span class="p">(</span><span class="n">fit</span><span class="o">.</span><span class="n">summary</span><span class="p">())</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>                            OLS Regression Results                            
==============================================================================
Dep. Variable:                log_GDP   R-squared:                       0.882
Model:                            OLS   Adj. R-squared:                  0.881
Method:                 Least Squares   F-statistic:                     3046.
Date:                Sun, 17 Dec 2023   Prob (F-statistic):               0.00
Time:                        18:33:04   Log-Likelihood:                -829.49
No. Observations:                 820   AIC:                             1665.
Df Residuals:                     817   BIC:                             1679.
Df Model:                           2                                         
Covariance Type:            nonrobust                                         
===================================================================================
                      coef    std err          t      P&gt;|t|      [0.025      0.975]
-----------------------------------------------------------------------------------
Intercept          22.0179      0.090    244.318      0.000      21.841      22.195
log_energy_cons     1.0960      0.020     55.939      0.000       1.058       1.134
log_rail_cargo     -0.0542      0.014     -3.808      0.000      -0.082      -0.026
==============================================================================
Omnibus:                       21.372   Durbin-Watson:                   1.409
Prob(Omnibus):                  0.000   Jarque-Bera (JB):               22.832
Skew:                          -0.365   Prob(JB):                     1.10e-05
Kurtosis:                       3.367   Cond. No.                         39.4
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>One thing I notice here is that while both energy consumption and rail cargo volume are significant here, rail cargo actually has a <em>negative</em> effect on GDP rather than a positive one. In the pair plots from the previous post, both rail cargo and energy consumption were positively correlated with GDP. This means that once energy consumption has been accounted for, higher rail cargo volume is actually a very weak indicator of economic success and is actually a <em>negative</em> indicator at that. This makes some sense if we reason through it. In a modern service-oriented economy, increased rail cargo volume indicates that the economy is still largely industrial, and thus not as productive.</p>
<p>Next, I tried a model that uses the control variables as interactions.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[4]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#fit regression model</span>
<span class="n">fit</span> <span class="o">=</span> <span class="n">smf</span><span class="o">.</span><span class="n">ols</span><span class="p">(</span><span class="s2">"log_GDP ~ (log_energy_cons+log_rail_cargo)*(urban_per+service_per+democracy)-(urban_per+service_per+democracy)"</span><span class="p">,</span> <span class="n">data</span><span class="o">=</span><span class="n">df</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">()</span>

<span class="c1">#view model summary</span>
<span class="nb">print</span><span class="p">(</span><span class="n">fit</span><span class="o">.</span><span class="n">summary</span><span class="p">())</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>                            OLS Regression Results                            
==============================================================================
Dep. Variable:                log_GDP   R-squared:                       0.923
Model:                            OLS   Adj. R-squared:                  0.922
Method:                 Least Squares   F-statistic:                     1217.
Date:                Sun, 17 Dec 2023   Prob (F-statistic):               0.00
Time:                        18:33:04   Log-Likelihood:                -652.94
No. Observations:                 820   AIC:                             1324.
Df Residuals:                     811   BIC:                             1366.
Df Model:                           8                                         
Covariance Type:            nonrobust                                         
===============================================================================================
                                  coef    std err          t      P&gt;|t|      [0.025      0.975]
-----------------------------------------------------------------------------------------------
Intercept                      22.1749      0.076    293.437      0.000      22.027      22.323
log_energy_cons                 0.8845      0.091      9.768      0.000       0.707       1.062
log_rail_cargo                 -0.1811      0.046     -3.937      0.000      -0.271      -0.091
log_energy_cons:urban_per      -0.0066      0.001     -6.163      0.000      -0.009      -0.005
log_energy_cons:service_per     0.0072      0.002      3.762      0.000       0.003       0.011
log_energy_cons:democracy       0.0292      0.012      2.531      0.012       0.007       0.052
log_rail_cargo:urban_per        0.0039      0.001      7.638      0.000       0.003       0.005
log_rail_cargo:service_per     -0.0015      0.001     -1.691      0.091      -0.003       0.000
log_rail_cargo:democracy       -0.0057      0.006     -1.035      0.301      -0.017       0.005
==============================================================================
Omnibus:                       16.319   Durbin-Watson:                   1.711
Prob(Omnibus):                  0.000   Jarque-Bera (JB):               22.052
Skew:                          -0.212   Prob(JB):                     1.63e-05
Kurtosis:                       3.682   Cond. No.                     4.92e+03
==============================================================================

Notes:
[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
[2] The condition number is large, 4.92e+03. This might indicate that there are
strong multicollinearity or other numerical problems.
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>In this model, the pattern remains, and in fact rail cargo volume is an even larger detriment to economy size than before. The only variables not significant at a p &lt;0.05 level are the interactions that rail cargo volume has with percent of GDP from services and level of democracy. This is counterintuitive. We would expect the GDP in economies with higher contributions from services to be noticably harder to predict using rail cargo volume; that is, we would expect the interaction to make the effect of rail cargo volume smaller. However, this is not the case; in fact, the coefficient suggests that if anything, it is making the negative effect of rail cargo volume greater. It seems that in large service industries, higher rail cargo volumne could indicate that more money is being spent on transportation of goods (a low value-add) which is a detriment to the GDP.</p>
<p>Also unusually, the results seem to suggest that weaker democracies and authoritarian states are not inflating their GDP. If they were, we would expect the cumulative effect of the democracy interactions to be negative---that is, in democracies, the same level of energy consumption would predict a smaller economy than it would in an authoritarian country. However, the opposite is true: a 1-point increase in Democracy Index results in a 0.0235 increase in log(GDP). This suggests that democracies themselves are either inflating their GDP (not likely, because parties outside power have an incentive to point out false economic statistics to delegitimize their opponents) or they have intrinsically stronger economies.</p>
<p>Our model accounts for 92.2% of the variability in our data, which is very good. The lower AIC of this model suggests that the interaction variables are a significant improvement over the previous model which just had the two variables of interest.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Let's look at the a plot of residuals and fitted values to see if there are likely to be any problems we need to resolve.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[5]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">'fitted'</span><span class="p">]</span> <span class="o">=</span> <span class="n">fit</span><span class="o">.</span><span class="n">fittedvalues</span>
<span class="n">df</span><span class="p">[</span><span class="s1">'resid'</span><span class="p">]</span> <span class="o">=</span> <span class="n">fit</span><span class="o">.</span><span class="n">resid</span>
<span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span> <span class="o">=</span> <span class="n">df</span><span class="p">,</span> <span class="n">x</span> <span class="o">=</span> <span class="s1">'fitted'</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">'resid'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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rz0G6joGoOifzZs3K6WUOnz48Lif88wzz9R07DNtomtVTKMG6nKv1fe+9z21bNky5ff71fnnn6+eeOKJ2gy4hsq5Vr29veqTn/yk6uzsVH6/X5177rnqn/7pn3JJi43iU5/6lFq0aJHyer2qvb1dfeADH8gFaaWcZLy7775bdXR0KJ/Ppy677DK1d+/eGo7YPdjmkoiIyMW4R01ERORiDNREREQuxkBNRETkYgzURERELsZATURE5GIM1ERERC7GQE1ERORiDNREREQuxkBN1GCUUvjMZz6D1tbWXG/yv/mbv5mx779ly5aG74dOVAkGaqIGs23bNmzZsgW//OUv0dvbiwMHDuCrX/1q7vXFixfj4YcfHvV3GFyJaof9qIkaTHd3N+bPn8+uRER1gjNqogbyyU9+Ep///Odx5MgRCCGwePFirF+/Prf0vX79erz11lu47bbbIISAEALbt2/H9ddfj2g0mvvYPffcA8BpRfjlL38ZCxYsQFNTEy6++GJs37591PfcsmULzjrrLASDQVxzzTU4ffr0zP6jieocAzVRA3nkkUdw7733oqurC729vXj55ZdHvb5161Z0dXXh3nvvRW9vL3p7e7FmzRo8/PDDaG5uzn3s9ttvBwBcf/31+O1vf4sf//jH2LNnD6699lpcddVVeOONNwAAL774Ij71qU/hlltuwe7du3H55Zfja1/72oz/u4nqGZe+iRpIJBJBOByGruvo6OgY83prayt0XUc4HB71eiQSgRBi1Me6u7vxox/9CEePHkVnZycA4Pbbb8e2bduwefNm3HfffXjkkUewYcMG/N3f/R0AYPny5di5cye2bdtW5X8p0ezBQE1Ek/LKK69AKYXly5eP+ngqlcLcuXMBAPv378c111wz6vVLL72UgZqoAgzURDQpUkrouo7f//730HV91GuhUAiAcxSMiKaGgZqIRvF6vbBte8KPrV69GrZt4+TJk3jf+95X9Gu9613vwgsvvDDqY4X/TUSlMZmMiEZZvHgxnn32WRw7dgx9fX25jw0NDeE///M/0dfXh3g8juXLl+NjH/sYNm7ciK1bt+Lw4cN4+eWX8Y1vfAP/8R//AQD4whe+gG3btuHBBx/EgQMH8O1vf5vL3kQVYqAmolHuvfdevPnmm1i6dCna29sBAGvWrMFnP/tZfOQjH0F7ezsefPBBAMDmzZuxceNGfPGLX8S5556Lq6++Gi+++CIWLlwIALjkkkvw+OOP49FHH8UFF1yAp59+GnfddVfN/m1E9UgobiIRERG5FmfURERELsZATURE5GIM1ERERC7GQE1ERORiDNREREQuxkBNRETkYgzURERELsZATURE5GIM1ERERC7GQE1ERORiDNREREQu9v8DV2LZmQm4plkAAAAASUVORK5CYII="
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The fit looks linear, and our correlation is very, very high, which is good. However, there is also heteroskedasticity---that is, the variance of our residuals is not constant across our fitted values. This is a problem because it means that our standard errors will be incorrect. Since we've already done the transforms that I would have tried for resolving this, we need to fit a model that accounts for this. Let's also check for normality.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Histogram of residuals</span>
<span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="n">fit</span><span class="o">.</span><span class="n">resid</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
class="
"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[7]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># QQ plot</span>
<span class="n">sm</span><span class="o">.</span><span class="n">qqplot</span><span class="p">(</span><span class="n">fit</span><span class="o">.</span><span class="n">resid</span><span class="p">,</span> <span class="n">line</span><span class="o">=</span><span class="s1">'s'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>I'm comfortable calling this good enough to say that the residuals are normally distributed.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Mixed-Linear-Model">Mixed Linear Model<a class="anchor-link" href="#Mixed-Linear-Model">&#182;</a></h3><p>As mentioned before, I wanted to account for the correlation within countries. A mixed linear model allows us to do a longitudinal multiple linear regression on the data. It takes into account clusters that form when observations are taken multiple times from the same subject. We can tell that different groups formed different clusters from the pairplot in the EDA, which shows the distribution of variable values differed by region. Because they differed by region, it is reasonable to assume that they differed by country as well, and this is the group that we are going to use here. Year also needs to be included as a variable to account for autocorrelation over time here.</p>
<p>First, I created a model with just the variables of interest:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[8]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">lmm_inter</span> <span class="o">=</span> <span class="n">smf</span><span class="o">.</span><span class="n">mixedlm</span><span class="p">(</span><span class="s2">"log_GDP ~ Year +(log_energy_cons+log_rail_cargo)"</span><span class="p">,</span> <span class="n">df</span><span class="p">,</span> <span class="n">groups</span><span class="o">=</span><span class="n">df</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">],</span>
                        <span class="n">re_formula</span><span class="o">=</span><span class="s2">"~1"</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">()</span>

<span class="nb">print</span><span class="p">(</span><span class="n">lmm_inter</span><span class="o">.</span><span class="n">summary</span><span class="p">())</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>           Mixed Linear Model Regression Results
===========================================================
Model:              MixedLM   Dependent Variable:   log_GDP
No. Observations:   820       Method:               REML   
No. Groups:         93        Scale:                0.0299 
Min. group size:    1         Log-Likelihood:       45.2410
Max. group size:    12        Converged:            Yes    
Mean group size:    8.8                                    
-----------------------------------------------------------
                Coef.  Std.Err.   z    P&gt;|z|  [0.025 0.975]
-----------------------------------------------------------
Intercept       -8.966    3.638 -2.465 0.014 -16.097 -1.836
Year             0.016    0.002  8.578 0.000   0.012  0.019
log_energy_cons  0.821    0.038 21.786 0.000   0.747  0.895
log_rail_cargo   0.032    0.020  1.600 0.110  -0.007  0.070
Group Var        0.484    0.479                            
===========================================================

</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Once we account for the differences between countries, increased rail cargo appears to have a positive correlation with GDP. However, its effect is also no longer significant. Let's look at a model that has the interactions as well:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[9]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">lmm_inter</span> <span class="o">=</span> <span class="n">smf</span><span class="o">.</span><span class="n">mixedlm</span><span class="p">(</span><span class="s2">"log_GDP ~ Year + (log_energy_cons+log_rail_cargo)*(urban_per+service_per+democracy)-(urban_per+service_per+democracy)"</span><span class="p">,</span> <span class="n">df</span><span class="p">,</span> <span class="n">groups</span><span class="o">=</span><span class="n">df</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">],</span>
                        <span class="n">re_formula</span><span class="o">=</span><span class="s2">"~1"</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">()</span>

<span class="nb">print</span><span class="p">(</span><span class="n">lmm_inter</span><span class="o">.</span><span class="n">summary</span><span class="p">())</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>                 Mixed Linear Model Regression Results
=======================================================================
Model:                  MixedLM       Dependent Variable:       log_GDP
No. Observations:       820           Method:                   REML   
No. Groups:             93            Scale:                    0.0287 
Min. group size:        1             Log-Likelihood:           39.3498
Max. group size:        12            Converged:                Yes    
Mean group size:        8.8                                            
-----------------------------------------------------------------------
                            Coef.  Std.Err.   z    P&gt;|z|  [0.025 0.975]
-----------------------------------------------------------------------
Intercept                   -6.317    4.014 -1.574 0.116 -14.185  1.551
Year                         0.014    0.002  7.164 0.000   0.010  0.018
log_energy_cons              0.623    0.103  6.037 0.000   0.421  0.826
log_rail_cargo              -0.013    0.050 -0.254 0.800  -0.110  0.085
log_energy_cons:urban_per   -0.006    0.002 -3.693 0.000  -0.009 -0.003
log_energy_cons:service_per  0.003    0.002  2.010 0.044   0.000  0.007
log_energy_cons:democracy    0.066    0.013  4.947 0.000   0.040  0.093
log_rail_cargo:urban_per     0.004    0.001  5.141 0.000   0.003  0.006
log_rail_cargo:service_per  -0.001    0.001 -2.089 0.037  -0.003 -0.000
log_rail_cargo:democracy    -0.025    0.006 -4.167 0.000  -0.037 -0.013
Group Var                    0.393    0.411                            
=======================================================================

</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Once country-level effects are accounted for, the effect of rail cargo is found to be insignificant. Democracy still has a cumulative positive correlation with the GDP, but it is much smaller. Once again, we'll go through the regression assumptions.</p>
<p>The data appear to be normal enough based on a histogram of the residuals and the Q-Q plot:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">sns</span><span class="o">.</span><span class="n">histplot</span><span class="p">(</span><span class="n">lmm_inter</span><span class="o">.</span><span class="n">resid</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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WdO2bdumlJQUDR061N920003KSUl5aL13nrrrdq4caOOHTsmY4y2bt2qw4cPa9SoUdEoOyihjNFxHP3v//6v+vTpo1GjRqlr164aOnSoXn311ShVHbxQ30vHcTR+/Hg9/vjj6t+/fzRKDVmoY/yqqqoquVyumN4jUJLOnDmjkpKSBp8XkpSdnX3B8Wzbtq1R/1GjRmnnzp2qq6uLWK0tEco4v8pxHNXU1KhTp06RKLHFQh3jypUr9Y9//EPz5s2LdIktFsoYN27cqMGDB2vx4sXq3r27+vTpo1/84hc6ffp0UNsm/MS5+hu2fvUmrampqY1u5hoPysvL1bVr10btXbt2vWi9v/vd79SvXz/16NFDbdq00Z133qlly5bp1ltvjWS5IQlljBUVFTp16pSefvpp3Xnnndq0aZO++93vasyYMSoqKop0ySEJ9b1ctGiREhMT9dhjj0WyvLAIdYzn+/LLLzV79myNHTs25jeX/PTTT+Xz+YL6vCgvL2+y/9mzZ/Xpp59GrNaWCGWcX7VkyRJ9/vnneuCBByJRYouFMsb3339fs2fP1h/+8AclJsb/DRxCGeOHH36ot99+W/v27dOGDRuUn5+vdevWafLkyUFtm/ATBjk5OXK5XBdddu7c2aJtuFyuBo+NMY3aIimYMTZVV3P1/u53v9M777yjjRs3qqSkREuWLNGkSZP0+uuvR2xMXxXJMTqOI0m67777NGPGDF1//fWaPXu2Ro8eHfWDSyM5zpKSEv37v/+7Vq1aFdV/n18V6X+v9erq6vTQQw/JcRwtW7Ys7OMIVbCfF031b6o93oT6ufjSSy8pJydHa9eubTL8xpNAx+jz+TR27FjNnz9fffr0iVZ5YRHM++g4jlwul/7whz/oxhtv1N133628vDytWrUqqNmf+I+GrcCUKVP00EMPXbRPr169Qnptr9cr6dy3s27duvnbKyoqGqXlSAp0jO+++64++eSTRuv++c9/XrDe06dP61e/+pU2bNige+65R5J07bXXas+ePfrtb3+rESNGtHwAAYjkGLt06aLExET169evQXvfvn319ttvh150CCI5zrfeeksVFRW64oor/G0+n08///nPlZ+fr48++qhFtQcqkmOsV1dXpwceeEClpaXasmVLzGd9pHP/zhISEhp9a77Y54XX622yf2Jiojp37hyxWlsilHHWW7t2rR555BH98Y9/jNpnSyiCHWNNTY127typ3bt3a8qUKZLOBQVjjBITE7Vp0ybdfvvtUak9UKG8j926dVP37t2VkpLib+vbt6+MMTp69KgyMzMD2jbhJwy6dOmiLl26ROS1MzIy5PV6VVhYqIEDB0o6t5+0qKhIixYtisg2mxLoGG+++WZVVVVp+/btuvHGGyVJf/vb31RVVaVhw4Y1+Zy6ujrV1dXJ7W44EZmQkOCfMYmGSI6xTZs2GjJkiA4dOtSg/fDhw1G/AW8kxzl+/PhGf1BGjRql8ePH69/+7d9aXnyAIjlG6f+Cz/vvv6+tW7fGTUho06aNBg0apMLCQn33u9/1txcWFuq+++5r8jk333yz/vu//7tB26ZNmzR48GAlJSVFtN5QhTJO6dyMz49//GO99NJL/i9a8SrYMXbs2FF79+5t0LZs2TJt2bJF69atU0ZGRsRrDlYo7+Mtt9yiP/7xjzp16pS+9rWvSTr3Oep2u9WjR4/AN96iw6URtCNHjpjdu3eb+fPnm6997Wtm9+7dZvfu3aampsbf56qrrjLr16/3P3766adNSkqKWb9+vdm7d6/5wQ9+EPenul977bVm27ZtZtu2beaaa65pdOrwV8eYlZVl+vfvb7Zu3Wo+/PBDs3LlStO2bVuzbNmyaJcfkFDGuH79epOUlGRWrFhh3n//ffPss8+ahIQE89Zbb0W7/ICFMs6viuezvYwJfox1dXXm3nvvNT169DB79uwxJ06c8C+1tbWxGEID9acOv/DCC+bAgQNm+vTppkOHDuajjz4yxhgze/ZsM378eH//+lPdZ8yYYQ4cOGBeeOGFVnWqe6DjXLNmjUlMTDRLly5t8J6dPHkyVkNoVrBj/KrWcLZXsGOsqakxPXr0MPfff7/Zv3+/KSoqMpmZmebRRx8NaruEnyibMGGCkdRo2bp1q7+PJLNy5Ur/Y8dxzLx584zX6zUej8d861vfMnv37o1+8QH67LPPzLhx40xycrJJTk4248aNM5WVlQ36fHWMJ06cMD/60Y9MWlqaadu2rbnqqqvMkiVLjOM40S0+QKGM0RhjXnjhBfONb3zDtG3b1lx33XVxex2jeqGO83zxHn6CHWNpaWmTv8Nf/T2OpaVLl5qePXuaNm3amBtuuMEUFRX5102YMMFkZWU16P/GG2+YgQMHmjZt2phevXqZ5cuXR7ni0AQzzqysrCbfswkTJkS/8CAE+16erzWEH2OCH+PBgwfNiBEjTLt27UyPHj3MzJkzzRdffBHUNl3G/P8j2wAAACzA2V4AAMAqhB8AAGAVwg8AALAK4QcAAFiF8AMAAKxC+AEAAFYh/AAAAKsQfgAAgFUIPwAAwCqEHwAAYBXCDwAAsArhBwAAWOX/AacTs9tMsLnQAAAAAElFTkSuQmCC"
class="
"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># QQ plot</span>
<span class="n">sm</span><span class="o">.</span><span class="n">qqplot</span><span class="p">(</span><span class="n">lmm_inter</span><span class="o">.</span><span class="n">resid</span><span class="p">,</span> <span class="n">line</span><span class="o">=</span><span class="s1">'s'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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4cOHMZlM9kd2uIo6deowc+ZMp12vc+fOTJo0yWnXK04mk4mlS5cCrvv3K3KzKQyJlFImk+m6XyNHjizuEm9o/vz5VKpUKUf71q1befjhh29qLZcvX2bq1Kk0aNAAHx8fAgICuOeee9izZ89NrSPLtGnTaN68eY72pKQkevbsefMLEnFhelCrSCmVlJRk//PixYt5/vnn2bdvn73Nz8+Ps2fPFkdpWCwWTCYTHh4F+/dY1apVnVzR9aWnp9O1a1cSExP597//TZs2bThx4gQzZsygTZs2fPfdd7Rt2/am1pQXPcxYxHHqGRIppYKDg+1fZrMZk8mUoy3LoUOH6NKlC2XLlqVZs2Zs3Lgx27U2bNjA7bffjp+fHyEhIUyYMIGLFy/a3z979izDhw+ncuXKlC1blp49e3LgwAH7+1k9PMuXLycsLAwfHx9+//13MjIyeOqpp6hRowblypWjTZs2rF27FoC1a9cyatQoUlNT7b1Z06ZNA3IOk507d46HH36YoKAgfH19ady4McuXLwfgzJkzDB48mJo1a1K2bFmaNGnCokWLHPosZ86cycaNG1m+fDn33XcftWvXpnXr1nzxxRc0bNiQBx54gKzHPOY25Na/f/9sPXELFy6kZcuWVKhQgeDgYIYMGcLJkyft769duxaTycT3339Py5YtKVu2LO3atbOH2fnz5zN9+nR27txp/2zmz58PZB8my018fDy9evWifPnyBAUFMWzYME6fPm1///PPP6dJkyb4+flRpUoVunbtmu3vWqQ0UhgSEZ599ln+7//+j7i4OOrXr8/gwYPJzMwE4JdffqF79+7cdddd7Nq1i8WLF/Pzzz8zfvx4+/kjR45k27ZtLFu2jI0bN2IYBr169eLq1av2Yy5dusSMGTN477332LNnD4GBgYwaNYr169fzySefsGvXLu6991569OjBgQMHaNeuHTNnzqRixYokJSWRlJTE//3f/+Wo3Wq10rNnTzZs2MDChQuJj4/n5ZdfxtPTE4ArV64QERHB8uXL2b17Nw8//DDDhg1j8+bN+f58Pv74Y7p160azZs2ytXt4ePD4448THx/Pzp078329jIwMXnzxRXbu3MnSpUtJSEjIddjy2Wef5d///jfbtm2jTJkyjB49GoCBAwfyxBNP0KhRI/tnM3DgwBveNykpiU6dOtG8eXO2bdvGqlWrOHHiBPfdd5/9/cGDBzN69Gj27t3L2rVrueuuu9DzvKXUK/yD70WkpJs3b55hNptztCckJBiA8d5779nb9uzZYwDG3r17DcMwjGHDhhkPP/xwtvN++uknw8PDw7h8+bKxf/9+AzDWr19vf//06dOGn5+f8emnn9rvDxhxcXH2Y3777TfDZDIZx44dy3btO++805gyZcp1665du7bx+uuvG4ZhGN98843h4eFh7Nu3L9+fR69evYwnnnjC/rpTp07GxIkT8zze19c3z/e3b99uAMbixYvzvFa/fv2MESNG5Hn9LVu2GIBx/vx5wzAMY82aNQZgfPfdd/ZjVqxYYQDG5cuXDcMwjKlTpxrNmjXLcS3AWLJkiWEY1/5+d+zYYRiGYTz33HNGVFRUtuOPHDliAMa+ffuM2NhYAzAOHz6cZ60ipZHmDIkITZs2tf+5WrVqAJw8eZLbbruN2NhYfvvtNz766CP7MYZhYLVaSUhI4MCBA5QpU4Y2bdrY369SpQoNGjRg79699jZvb+9s99m+fTuGYVC/fv1staSnp1OlSpV81x4XF0fNmjVzXCeLxWLh5ZdfZvHixRw7doz09HTS09MpV65cvu9xPcYfvSbe3t75PmfHjh1MmzaNuLg4UlJSsFqtACQmJhIWFmY/Lq+/l1q1ahWo1tjYWNasWUP58uVzvHfw4EGioqK48847adKkCd27dycqKop77rmHypUrF+h+Iq5CYUhE8PLysv/ZZDIB2H9BW61WHnnkESZMmJDjvFq1arF///5cr2kYhv1aYJuw/efXVqsVT09PYmNj7UNaWXL7ZZ0XPz+/677/73//m9dff52ZM2fSpEkTypUrx6RJk8jIyMj3PW699Vbi4+Nzfe/XX38FsIcxDw+PHMNKfx4uvHjxIlFRUURFRbFw4UKqVq1KYmIi3bt3z1HT9f5eCsJqtRIdHc2//vWvHO9Vq1YNT09PVq9ezYYNG/j222956623ePbZZ9m8eTOhoaEFvq9ISacwJCLXFR4ezp49e6hXr16u74eFhZGZmcnmzZtp164dYJu0vH//fho2bJjndVu0aIHFYuHkyZN07Ngx12O8vb2xWCzXra9p06YcPXqU/fv359o79NNPP9GvXz+GDh0K2ALBgQMHrlvbXw0ePJhnn32WnTt3Zps3ZLVaef3112nZsqW9R6dq1arZVvJZLBZ2795Nly5dAFt4On36NC+//DIhISEAbNu2Ld+1ZMnPZ/NX4eHhfPHFF9SpU4cyZXL/8W8ymWjfvj3t27fn+eefp3bt2ixZsoTJkyc7XKOIq9AEahG5rqeffpqNGzfy6KOPEhcXx4EDB1i2bBmPPfYYYOs16devHw899BA///wzO3fuZOjQodSoUYN+/frled369etz//33M3z4cL788ksSEhLYunUr//rXv1i5ciVgWzV24cIFvv/+e06fPs2lS5dyXKdTp07cfvvt3H333axevZqEhAS+/vprVq1aBUC9evXsvR179+7lkUceITk52aHP4PHHH6d169ZER0fz2WefkZiYyNatW7n77rs5cOCAfSUXwB133MGKFStYsWIFv/76K+PGjePcuXP292vVqoW3tzdvvfUWhw4dYtmyZbz44osO1ZP12SQkJBAXF8fp06dJT0+/4TmPPvooKSkpDB48mC1btnDo0CG+/fZbRo8ejcViYfPmzfzzn/9k27ZtJCYm8uWXX3Lq1CmHgqOIK1IYEpHratq0KevWrePAgQN07NiRFi1a8Nxzz9nnsADMmzePiIgI+vTpQ2RkJIZhsHLlymzDPLmZN28ew4cP54knnqBBgwb07duXzZs323tM2rVrx5gxYxg4cCBVq1bllVdeyfU6X3zxBa1atWLw4MGEhYXx1FNP2XtNnnvuOcLDw+nevTudO3cmODiY/v37O/QZ+Pr68v333zN8+HCmTJlC3bp1ad26Nbt372b37t00atTIfuzo0aMZMWIEw4cPp1OnToSGhtp7hcDWczR//nw+++wzwsLCePnll3nttdccqgfg7rvvpkePHnTp0oWqVavma7uA6tWrs379eiwWC927d6dx48ZMnDgRs9mMh4cHFStW5Mcff6RXr17Ur1+fv//97/z73//WJo5S6pmMvw5ui4jIDX399dcMGDCA1157Lds2AyLietQzJCJSAD179uTrr78mJSUl26aFIuJ61DMkIiIibk09QyIiIuLWFIZERETErSkMiYiIiFtTGBIRERG3pjAkIiIibk1hSERERNyawpCIiIi4NYUhERERcWsKQyIiIuLW/h8YOfzkzg7JngAAAABJRU5ErkJggg=="
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>There is a somewhat long left tail, but we have enough observations that I don't think it should really matter that much.</p>
<p>More concerning is that, according to a fitted values versus residual plot, our data is still heteroskedastic.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">'fitted'</span><span class="p">]</span> <span class="o">=</span> <span class="n">lmm_inter</span><span class="o">.</span><span class="n">fittedvalues</span>
<span class="n">df</span><span class="p">[</span><span class="s1">'resid'</span><span class="p">]</span> <span class="o">=</span> <span class="n">lmm_inter</span><span class="o">.</span><span class="n">resid</span>
<span class="n">sns</span><span class="o">.</span><span class="n">lmplot</span><span class="p">(</span><span class="n">data</span> <span class="o">=</span> <span class="n">df</span><span class="p">,</span> <span class="n">x</span> <span class="o">=</span> <span class="s1">'fitted'</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">'resid'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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AIVSqJKEbzw12FKLVkhMCxEiRKtYVTVqAHWLGue87jUAcBwHb3/72/Hxj38cZ555Zsvbv/3223Hbbbf5/87lcivKWIc1zeXFroEMdv7yMJ45NgXTYZApAWMclACKRMEYB+McskSwvj2CE3kTdz1yGJdu7pw1sj4ZwZUQIUK8vLBqDHVXVxckSaqLnsfHx+uibADI5/P49a9/jd/85jf4sz/7MwAAYwycc8iyjIceegivf/3r676naRo0TVuagzhJNKtpemIbYU1zceGd75mSBYcJohgH4LihNOeALFEwzmE6DIbNqyLh89alm257KYhpIUKEOD2xalLfqqriwgsvxMMPP1z1+sMPP4zLL7+87vOpVAp79uzBc8895//3vve9D2eddRaee+45XHLJJcu164uCsKY5Oxa7HBA83+moDICAUgKCSpRsu44fgTDaNmMtt2gtRHAlRIgQL0+smogaAG677Ta8853vxEUXXYTLLrsMX/jCFzA4OIj3ve99AETaenh4GPfddx8opTj33HOrvt/T04NIJFL3+mrAfGqazSI5xnhLbUirDUtRDgieb84BQuD/SSDq05xX6tSEADKlLUfCnuDKR7+/B2M5A20xBZokvj/jsr5rBVdChAjx8sSqMtRve9vbMDk5iU984hMYHR3FueeeiwceeAAbN24EAIyOjmJwcPAU7+XS4GRrmqdrbXupygHB800ooMkSdMuBLBHfaHMI54cBiCoUmkxwIm9ie3+ypUjYE1zxrkuWcSiUYHt/ctVflxAhQiweVlUf9anASumj3jOUxU1f+zXimoyIUl/TLFsOSoaNu995UV1Efbr26zLG8e57nsb+0Rz6UpGqTAPnHGM5A9v7ky33NQdRe74Lho3h6TIY5yAEsNxCNQUgSwRdSQ2mzRd0Pk/XTEeIECEWB6umRv1yx0JrmqdzbXspW5x2rElhc3ccE3kDubIFiRCsaRPnz6tLEwASJYiqMsDRVHp0LlBKcN66NK46sxvnrUuHRjpEiBBVWFWp75czFlrTXIza9krFUrY4BcVNsrow1JpMkY4JRTJNpviz39qK89e1YaZshZFwiAUhzKaEaAWhoV5FWEhN83Tu112qFqdgqaAvFcFMyYRhOyiZDsqWg/UdMbz3tZvx9os3hItqiAXjdOWNhFh8hIZ6lWE+QySA07tf1ysH7B/Noy9F62rUMyWrZWKXh9pSASEE7XEFU0UTkwUDps0xMl3G539+CA/uHQsX1RALQqiJEGI+CGvUqxDzqWmezv26C5kpPRcalQqKhoNM3oTDBHEMEEIn3qLaimRoiBAeTmfeSIilQWioT3MshTFbSZjvTOm5UFsq4OCYyBu+TKhEhDqZREm4qIZYEEKd9xDzRZj6fhngdO/XnW85YDbUlgp0k8GwHUiuKhkD98VNVjsZL8SpwenMGwmxNAgN9SrFfNmii2nMViK8csDJorbuLWRCAUJFqcBmHFGFIqKIRTZcVEPMF6czbyTE0iA01KsQC2WLLpYxO51R2wYXVSgADocBjAMSIehOVsRVTvWiGrb3rD4sBQkyxOmNUJlsDqwUZTIPp6vK2EpD0BmaKBhwGEdUkdCTiiChCf/2ZNXPFnMfT1V7z0IdhZe7g1F5jp2GmgjhcxwiiNBQz4GVZKiXUjIzRD08Y/L4wATue+IlmDZDe1xdEYvqSnDYFuoorAQHYyWg6jy4vJGX43kIMTdCQz0HVpKhPhm9byCMYk4GK2lRnc1hY5xheEbH2rYo7rj+PJy3dmkkSRfqKKwEB2MlwbYZfrR7FMMzJaxti+HN5/dDlsNmnBDVCGvUqwgnwxYNo5iTw0oi4zVr7ykYNibyBnTLxv5RC++59xmsa4/hmh19uGJr16LtbyNRGACIUAl9KYqxnIG7HjmMSzd3Vv3eQr93uqLRM/m93wyFz2SIOoSu2ypCkC3aCM2ITV4Us380h7gmoyepIa7JoWDHPLFShmc0cti86V665YC6BjBXtrF7aAafevAA/uc9T+Hd9zy9KNd6oX3AYf9wBeEzGWI+CA31KsJCVMZCFaTTD7UOW60oC4NgqDuMQaZifnbZZNg3klsUI9BKZsdqkNlZ6PdON4TPZIj5IjTUqwitqIxds6MPjw1ksGco69ekD48X0BZVoFsMed1C2XTEqMaXWRRzuqDWYQuKsnDOYbuzsmWJQKIUMqWwGENbVFkUI7DQzM5Cv3e6IcwshJgvwhr1KkMzlbH+tAYA2PmLgaoa9OVbulA0HGTLFkzHFe8ggCZTdCcjiClSKNixylDb661KBIxxEAlwXCOtUAJKhB9OAHAOOJwvipLaQvuAw/5hgVCZLMR8ERrqVYhaYtPxqRK++OhhFE2nbhLP3pEc8oYFAjFIghCAAyhbDMPTZXQl1ZdFFHO6IeiwHRjNgwNgDFBkCm4zSFLACAK+7OliGIGFzkZf6PdON4TKZCHmizD1vUrhEZteu7ULD+4dQ9F06updvSkVed0C5/AjaUIIKCFQKIHDGSbyBjZ3x0/7KGapwBjHnqEsHjk44ZcblguXb+3CvTdejC+9+yKc059CQpOxJhVxU+DiM57sqSYL2dPFMgILHYay2ENUViNO54l2IZYGYUS9yjFbvcuwODjnoEQQimyHQ6Lwo2pwgAF447n9p30UU4vF6ClfCS1vlBJcsL4NH33Tdnz0+3uQM2zIlMK0HUgSgcMqsqcAFjW9vNCWtZXU6nYqEGYWQswXoaFe5Zit3uUPlCBAZ0JF0XBg2A44E69FFAmyRLG+I3YK9vzUYTEMbDPhDq+9Zrmjw2AqfN9IDqbtwHY4FIkiHZVhOwxjOQsJTa4yAifrsCxUP/7lrjt/uk+0C7G4CA31Ksds9S4xilH8Pakp6E5q0E0GmzHIlAKEo2Q4L6ta2EINbNCgtUUV7PzlwIoT7ghGqt946hh+vGcMJd1GpmCCAEhGFbzjkg3+8a2EjMDLGS/3zEKI1hEa6lWO2Zi0mkL8f2uymKccVSUAUpU2+MulFrZQZaxagwYA2bKF7uTc7TXLHTVSSpDXLTx5ZAqaRNDeHgUlBIxzlEwH33hqEDvWiH1aSRmBxcBqlMh9uWcWQrSG0FCvcsxV7+qMq+AATuTN06oWtpBFeT79q97i2SgCny6ZsBxBxFNlyZ+m5eFUttcEnZH+dLTqONNR4Zzt/OVhAHzFZQROBmF2IMTpjNBQnwaYrd5105WbcWyyhH9/ehBjOR0AoEp0VdfCFrooz7d/NWj0elMaDIujaNqglEAigMM4JvI64mq8yiCeyvaaVpyRF8fy4ODzclhWMlYaXyBEiMVGaKhPEzSqd2XLJu5+9Ihv0AgIelIa/ujiDXj7xRvqBiashrThySzK8+1f9YyeJkt4abIsiHguOY8TITJi2Ay6xdySwqkX7mjFGTEdBnCcFoIbq3nQx2p55kKceoSG+jRCsN61ayCDj/3ghTqDdiJn4EuPHcHmrviqIxWd7KI8X2WsqZKJoilGh3IAEiUgVPSkM8bAIVreiqYNTV4ZJYVWnBFVouDgp4XgxkLKGSsBq+WZC7EyEAqenAIspUgGYxzPH5/B3z2wHzMlC70pranov20zfP3Jl3Drt5/DnqEsYpp0UlN8llr842Q1kmu10kumjaJhI1MwMDRdRlylVQZW6KM7/rALSgQhjxICRab+w1PQLQxnyyjq1rILd9Se8+19yTnFNM7qS+LsvuRpIbix0gZ9BK/H88dn8PzxmbrnIZycFWK+CCPqZcZSetLetveP5jBVNEEJ8NIkR3dS8wlPnkHbN5LF7//bLuwfzcNyGCQK2Kzy2fmmDZcjQlgMjWSvnn/nT/fjxbECbCYGRCgSxfqOaN3nfTvGIUSzXTiMgwXekghBbzqKm67cvGxGutk5v3JbF45PlZqKadzyui0AMKvgxk1Xbl4VadmVJMcZvB5Fw0HZcny9grgqYUtPAjdduRl3P3pkVabqQ5w6hBH1MmIpPengtlWJgrpSobrlYHi6jIJh+5+1bIbpkoWB8QIY51BkMWUp+Nn5TPFZrgghuChzcJRNpzINDHxei3JOtxFTJfSlIjijM471HVGMZo2q/Z0pW4gqEiRKYDEOxoXSm8WY36ZFCdAZ19ARVzE0XcbHfvDCskREs53zbzw1iHdcsqGhTOcnrzsXyYgCi3H86Ws34+y+RN1n3nHJBtz96BHc9LVf40Pffh43fe3XizbLerGxUuQ4g9eDEKBs2XAYg+0wlNznaf9oHh/+7m7sG8mGk7NCzAthRL1MWErSS+22dYuBEAOEEMhU1FEn8gbimgRwYDxvAABSERkTBRMUot+aSNWfbRah1ot/LA+Zx1uUdw/NwHZ41TQwVaKQJYLz17XNuih756po2FjXXt2+FElJVfvbEVMR1yQkIhKyZQuGLX7PcVOYMhWLqyJRt6ywPBFRK/fSo4cy+PI7L8JPXhjD8EwJa9ti6IqrVeRCRSLY3J3ALb+1Fes7Yj4BsRG3YaUyqFeCHGdVd0BSw0tTJThcZGngSvdmyxY2dkYxNFVGyXLQ60q61mI1EflWKk5Hkl5oqJcJS0l6qd12RKHQZIqyJSJMiRIYtgPdZOCcw7AdaLKEmCaDFE0/q0tAIFH4nwVBXYRam27l4MjrNroS2pKTeSgluHJbF544PAmHcXfeMsA4UDLFPOYrt3XN+lDO5zoEyWcbO2IwbEEcm8jrIAAYCCLusIulON6TOYZ9Iznc8MUnMZ7TYTkcjDMUTQeaTNGTjECVKAzHwQsjWRwaz+MDr9+G12zuxI33PuM7ACDwlezSERlZ3VpSJ2ShC+ypluMMXg/dEl0ABJVqiff8GRZHKqqgYNjIGzba3OeKg/vn2XH3fTUQ+VYiTleSXmiolwlLOYO2dtvEHcIwPF2GxcQgDsY4SqaNguGAAOhJaYgqUsCgi+8RAnAGWI6DosmqWNDNxD9Mh2E8p0OV6ZKKfzDG8eihDGKqBIeJiNpxdctjqgSJUjx6KIP3XLG56QI/n+sQjNY8wRhFEpOpOKkMu6hSg1uGiGiuY7AchhlXlKU3FYFCCY5NlmBYDI7DYcc5bOZgIm9At2xkGfCJH+3Dd399HMeny+iIqyia4v1gS5pMKfaN5JbECTnZBfZUynF618O0GU7kddhuxsVh3D9vnAvt/WREBqUE2bKNdFSpOs+McXAAqaiCbDmMqOeL07mfPqxRLxOC9dVGOBnSS6NtJzQZa9ujiCoUTLTNwnI4NnfH0ebexJ5Bl0ilBiuYqRxZ3a5KG9amWyOKBEJFjZZAENHGsnpdnXAxyTxe5NKbimBTVxwbO+JY1x7Fxo44NnXF0ZPSmtb3PDbusYmiqGfbTt1nOOfI6hYch2GqYIIxXjeWMa+LWr8mSVjbHq1zTJaDvDTbvcTBMZ4zwAF0JwTj33REXV2RCTiAsWwZw9Ml6JYDiVIospAYPTRewEzJRK5sYXi6DN1yQAnxGe+m7WCmZOLxgYlFPZ7F4jh47YlXndmN89ally3d2RFTwTjDSLYM066+JowLx4lDGGzT4UhFFMQ1CcenSzg+VULZdPkjRETfjGHZuA6nCxqtT406XZZzDO1iIjTUy4SlJL0023ZCk7GxI4aEJuOc/hS+9O6L8N2bLsM5a1L+Zz2DHlEoHMaFMAoh2NGfqvJAa9OtBcPG4fEChmZ0MC4cgbLl4NB4wSeuLTaZJxhJEiJ0y5MRBVFVAiGkaSvOroEM3n3P07jpa7/Gv/5iAHndxktTJeR1y/9MwbBxNFPEyEwZecPGpx484BOovLnPd7/zInzuhlfgvHVtiKqCyRvEcpGXZruXyu6EtIgs+SIs3hQ1ClEG0S3mlw4oIaAunT0ZUcABTBQMOA1a0iRJGPoH955YtAXPthn+4cEXMVU0kY4o0GS66hbY7X1JOFzUomXXeQUqqW9vzzWZYKZk4Zw1Kfz9758H4mqwexmZqCJhXXsMGzqiq+K4VxJOtnVzpSM01MuE2h7esiVSXWXLwVjOWDDpxavrXb6lC4pEMJbTq7btpWw/+qbtuGB9G2SZ1u8H53Ac7pOkYoqEmnu9ykgWDFtEAlZ9RGfYDIOTRUwVzZM6rkZYCOu7UbTWldDgMI7BqRImiwZyZQtD0yWUTBFBrmmL1kV0XrT2urN78BfXnIVkRF7U6zgfzHYvZQqCKNidrHAGvClqIlci/qNUvMC4d905YgqFIlEwDhAIJTsPnHM4DNBkCSey5UVZ8HYNZPDWu5/AnqEZFE0Hg9MlHJss+o7eallg94/lIRHhBDFOIJHKmfO7+zjHcFb374/2mIaoTLG2Lepnhc7ojCOhyavmuFcSVlo//WIjNNTLiNo0arAlZiH1k2Ck+JXHj4oZxIxjumjOuu3gfkwXTQxNlWA6DFFFwoaOGHpSERwYK1SlHT0jaTgOJvK6b9QJUGfUHQ5kCgbO7ltc8Q8vkhzP6zg6UcRLU0UMTZfx0lQRRyeKmMjrVdFss3RYR1zFho4YJEqQyRsYninBYRwxVcL6jhhSEWXWiG4xruPJisM024dN3Qm0xxSocuXR9siFNuNgbt8454DpMBg2g8WEET6RNxB1iXHMNeKci5KIxTgkQtCT1GBznPSC5zlQRyYKAOBGogRli1W1E66GBXaqZIIS4mamJICIZ0IQNCsR9tq2qH9/TJVM2AxIRZSqrJCH1XDcKwlLWVpcCQjJZMuMxSK9NCNOTBVNqDLFuy7biCu2djfd9uVbu3DxGR14691PwHIYuhNa1WJR22rkGck9w1k3gnX1P0hFFEQwXMUiH1UkfPias3DB+raTOV1VmC/re7Z0WDKiYGMnQaZggjPBxk3HlKoocjYW98lcx8Vipjbah+19Sdx47zNVMqkVcmEJlluat2scA0ki0G0GwxbXUUTW3CeSRRUq+AyUQHHYSS14QQeqO6GhbDmAp/hGASsw7GQ1LLCekVAlijO6Yj6DW3Ktdcl0YDkMd1x/nv88rCShltMB85UHXm0II+pTgJMlvcxGnOhPR2A5HLsOT85pOPaP5TGe09GbiiCmyQCBn07WLYa2mOwbKS/dqskiNQq4adSAkVYkClmifl1upmw1/uEFIsj6jrn1V8+BFq/JePRQxo9O506HSe7+E6Qi1Ua68pnmkc1CruNii8PU7kPD0gbjkChBRJGhytVHSQmgyhQKpZCpYCpLlCCmUGxoj1WlZeOqtCg1+KADFdUkaLJg8XNwt/efwLAZyqazKuRMg5wBcPjciZgmIyJTlE1HtLsB/r25UoRaThcsVWlxpWDVGeqdO3di06ZNiEQiuPDCC/HYY481/ez3vvc9vOENb0B3dzdSqRQuu+wyPPjgg8u4t0uDxSJO1Nadj2VKVenk0RkdRdPxjdTlW7vwgddvgywFok6IxV6RKCRKqgRIFjsamC/ru5V0mCoJ1vNypMyWi5naLC1+wfo0Pva75yAVVSC57WWKREGJV6sWrOOYKiGiysjqNmRJpM11m/kLnicvutC0fRUpEATdSQ2UENgOh80YmNtPPFFYHQtsMyMxWTRwcLyAvGHj+HQZN3/9WZ+gOB/DstQa+qcLFru0uJKwqlLf999/Pz74wQ9i586deM1rXoO7774b1157Lfbt24cNGzbUff7RRx/FG97wBtxxxx1oa2vDPffcgze/+c146qmn8MpXvvIUHMHiYLF6sj1DNlO2MJE3wDivmhClWw5gMxyfKvnfefvFG/DTPSN46ugUGAdk6jKDCQEHh+0wUEpwVt/ip5kasb6BStqw9rhbSYed3ZcEwHFgrLDkKbPlnPTULDX/2EAGqkSxriOGyYIp+qTdXvSIIqEzoaJkOnjXZRux6/BknYDIldu66tTN5pu2r037JjQZHXEVEwUDtlMxQgzAOy7ZsCoW2FrRlQnTQcGwQQnQl4qgLao07OmdS6jldBXwWCqcyn76pcSqMtSf/exn8Z73vAd/+qd/CgD4x3/8Rzz44IO46667cOedd9Z9/h//8R+r/n3HHXfghz/8IX70ox81NdSGYcAwDP/fudzKY10uVn1rx5oUNncn8NTRSTDGocgUVXxVIqLln70w6s+vppTg/b+1DQMTz2EibwhSmQSAcTd9CXTGVdzyusWPguZ73K3IS7YyoGKxIrqlFL1phODYUw/N6qkypYioFLrFoFCGK7Z246Yrt9TNN/+rH7yAbMlCTJVc8Q7MKShRqzjmTfjyHKii6WCqKI5ZdjkHikShUoJvPDWIHWvSq8IoeUZiz3AWH/3+HgxPl7G2PQJKxPVuJKs7m2FZbQIeK0W6s9F9v9qxagy1aZp49tln8ZGPfKTq9auvvhq7du1qaRuMMeTzeXR0dDT9zJ133omPf/zjJ7WvS43FIk5QSvDGc/vwxJFJ97uAkMwQZCOJUHQlVRyZKFZFeZdv7cLnbnhFZQKVU5lAdWZvArdfu31JFpCFHHer8pLLIUG5EghE1edQq8pK1J7D4ILHGMdbPv84hqdL4BzI6RYoEe1a3clK2r5WXnTuCV86ioYDhzFIEoHDRI26Px0BJYKJ/rEfvIDP3HABLljXtqwL/0IMD3UzTNNF003pVztljTInjQzLUs4GWAqEkf/SYtUY6kwmA8dx0NvbW/V6b28vxsbGWtrGZz7zGRSLRdxwww1NP3P77bfjtttu8/+dy+Wwfv36he10C1joYtDqIIK5tr++I4aEKsNmrGrIhcfyjSkSxgtGXZR3+dYu/PD9V2DPcBa/OT4DwoFXbGjDjv4U9o/l8cjBiUX3qhc6gKGVdNhypMxWAjN1oefwm08PYu9IDsHyKOOAbTowpsvoTUXq0vaNIkLDdrBnKIuDY3n87vn9ePalabwwnAWI4DdEFYqEpmAsp8OwhKLXEaOIG+5+Amf3JZfECWz0jDx5ZHLBhmcxMifLWSY5Way2yH81YtUYag+1Ny0PKPvMhm9961v4m7/5G/zwhz9ET09P089pmgZN0056P1vByXihi1Xf8iZExVQVAKmkQRVhSMqW0zTKo5TggvVtfsvJroEMbrz3mSX1qhc6gKGVdNhSp8yWY9JTK46fdw53/vIwXhzLw3RJdWf3JXHL6+rPIWMcX3rsCJpxmGzGMVkwkIwovvFpFBEWDDHQxLAZsjrHN54axJbuOCKKhK6EBkWisBnD0HS5rn3McY/r1m8/h8/d8IpFu58aPSOdCRXjbllnIYZnMTIny10mWShqr/NyD3J5uWDVGOquri5IklQXPY+Pj9dF2bW4//778Z73vAff+c538Du/8ztLuZstYzG80MWob9WmQgmpLCzzifKW06tezYSRpZz0NH/HT7REif9xcM5wJFOExbhfS94/lsczL01haLrsfyvoF3udRbrNkODcNz6NJGeHp8tCmpSKfmmHMRyfKkO3mT+w4uhkxUiTgP6mTAkczjFVNLHzlwP+wn8yddFmEf+BsTwcxrGhIyYETDC/lPNiZE5WQpmkFQSv83IPcnk5YdUYalVVceGFF+Lhhx/G9ddf77/+8MMP4y1veUvT733rW9/Cn/zJn+Bb3/oWfvd3f3c5dnVOLGb9aTHqWycb5Z2KetpqJowshaPRqqPEGMc3nx7Ev/zXIRi2g66EBk2WMFM28fSxaTx5dBoJTfYNo0QAw+JVEW6w7TeoZS27IinMjfS8iJBzIWDicOGUEELACcAcoCOuQM86GM8b4r5zZWkJ4DoQgtBIKQHhBA7jODCWx96RHPJutLaQDE6ze9b9ZRAAmYKJRET2CZatppwX45laCWWSVuBPDnMYRmf0us4R03Zg2g4eH5hYtc/rSsCqMdQAcNttt+Gd73wnLrroIlx22WX4whe+gMHBQbzvfe8DIOrLw8PDuO+++wAII/2ud70L//RP/4RLL73Uj8aj0SjS6eW/aTzv/79fmsb+0RzaosqS1J/mW9862ShvNdXTFoKlYLMupqPRqqPEOMe/PXIEzxybgukwyJTAyukijarb4K4x1i0bjisrKktETAhrkmENJqhP5HT8yVefxjlr0rhmR19Fl50LDXjZNdIA/IhLkST0JCMYy+k4kTfBAl6Ap34nS143gnjPcjgeH5jA/c8cX3AGp9k96w0wCc5wj6rNWwCb4WSfqeUokywGvMh/PCfaO2WJBBwboXhnOxwP7j2Bm6489fu7WrGqDPXb3vY2TE5O4hOf+ARGR0dx7rnn4oEHHsDGjRsBAKOjoxgcHPQ/f/fdd8O2bbz//e/H+9//fv/1d7/73fjqV7+6rPseTEsWA8MkelKRRZ/hvJD6VjDKmywYmC5ZaIsLHWLG+KwP2Gqppy0Eq4HN2sjocHC/VhhVRPrxw9/djbIpGNYKJWAAioaDIqpHfho2dxXLCGwGFF3d7blACJDTbTx/PIvBqRI6EypGswbiquQbZpFiB2yHQZUlX4e8YNjojKs4NulOXoOIpGWJCilOVJwCRSJ4cO+Jk8rgNLtnvQEmIGIuu80Ygr3680k5n2zmZCnLJIuFHWtS6EkJR0umBHMNclmNjvpKwKoy1ABwyy234JZbbmn4Xq3x/eUvf7n0O9QCatOSEUVC0bCgW47ba1k91/hk608LrW9RSpDXLXz5V0fnZZhWSz1tvphv3f1U9ZHWGh1B2qrUCgGxYAomv+YOvCB+W10jiKEcADiH2fxjVVAogc1F7bmg20hFZMRViqwrJWszDsfVDwfEUJBjkyWkowriqoTP/sEF+Jsf78We4Sw4E9Km3sLPuVAto4RgbVsUJ7Llk8rgNLtnPcehbDp+jdXDQlLOzTInrd4rK52PQSnBNTv6sHtoBg7nIJz7uQ87MMilZDmr0lFfKVh1hnq1oVFakoMjosgomzYczvwBBISQRak/LbS+tVBC2Gqpp9VitsWyjs0KQLcqbNaZcjWbtTbyBoCelIY/uniDLxazVAgaHdviGJ4uV9UKbUf0xpsOc+eNo6lkahCWw+f8jAeZElBKIXNRr0xoMkZmdNzw6vXYfXwaTx+dhuWm1impRK4l00bJtLGhIwZCCT509Vn48+88j4m8ActmQpYWHI4jFv90XMY1O/pwz6+OnVQGp9k9SwhBV0LD4FQJlBCAiJr7Yqac55ulWel8jCu2duFLjykomwwWq2/xXIxBLi93hIZ6idEoLenpGw9PMziMQbeYmIVMyaIsBgupb50MIWy11NOCmGuxrGeziraiajZr1ic1eQ6OJksomRYMW8yG/uv/2Iv7nxlcMhEYIGh0ciibTlWtUIypFJ9jHMjqFiRCYKF1I9wKqHu/MM5hO0KnGwDuf3oQ2/tT6EpqGMvpoBB1SwrADuzb8ekSbv76s9jSk8CfXrEJ//H8CA6eKMC0WYWs5qZWf/DcCHTLRk6nSDfgebSSwZntni0YDrqTGnqSGiYLJrLMXlRm/lJ2R5yKrM6ONSmcsyaNfSM59EcjLrNftHgCwFjOWJGO+moC4bWjW0JUIZfLIZ1OI5vNIpWa/432yMEJfOjbz6MnqdU9MAXDxnhOR9lykIyI9N9i1j+rjJFb32q2/T1DWdz0tV8jrsl+S0oQZctBybBx9zsvaurd7xrI1PXmntWkN/dUotliOV0yoUgU77rsDMQUCf/6iwHEVAmjWd1vK6qk9YTR/vOrz8KTRyaxfzTnR5FeNAsIo0UpwZp0BHf+3vlLdh52DWTw5995HidyOiRKIBHipx8pAAYOSgiYUIat61OeL2RKKm1UEGlqDsC0mfu+cEj70hHkDRt53UZ7VHZHaTIwBjju0iNRsY3+dBRliyGhSfjkdefiaKaIz/2nYKe3x1RIFBjPCX1y7zhiqlTF8+Cc+4bh3hsvntNIzfaMLHbKmTGOd9/zNPaP5mqY5vPf70Z4/NAEPv3QQRyfKoFxjqiyuOvJbKg8U05DRz0UPTk5hBH1EsNLSxqOA9ikSlc5ocmQ2iLIlmy8//VbceGG9kX1gOdT31o8Qlh1by4WOXI7WQQzB70pDYbFUTRtmLaoqxo2w2ceehHpqIy8biOnk6q2IsCdu00IbM7xw+dGkC+baIspGMvWMl8JZImDcY5s2V5S4YfLt3bhXZedgc8+/CLARbTqpR+7khoyeRMlwwbDyY/MIxCRs+e0ELeXyrJ54H0gpoqIlxIgW7JQthjO6IxBtxiGs2Vw2z2vVDCDJUrQl9IwljPwb48chjD1HH3JCAqmjbGsCe46TDYT0XjRdDA0XcKadBSKTOedwal9RtqiCgAxonXvSG5Rn8fa7FqQ8CdTWjVWdr6p7i8+ehifefggTJuJO4+IUs3uoZllUQdbDcS31YzQUC8xdqxJoTOh4sBY3p07S0CIYEJ2JVQUDAfb+5N416UbF7QgzJXqarW+1YhcwzmHbom6k246cByGqYLZkAXeLEo9MFZYUTKC3mKpyRJemizDsB04jFepbtmMI6/brjHgVW1FgHBAGBfXMJPXodsMus1Qtpw65iuBaEWKqtKSt6hdsbUL9+06KpjSlFQpzBEAR132dlBIZCEIziH3XvAGsnjbl6moTwJiZrgwHA50i4EQ0Q8tRmwSYfT9urUggx0Yy8N0o++ZckkMf4GobwMEiiSMtULFPTuSLaMrri7IMHjPyK6BDD790ItLxvCvHStbKw6iuvPc50u6evzQBD7z8EEYFoMiicE5nAOWw2A7AGAuizrYSie+rWaEhnqJ8eSRSV+OkACQJAAcKJs2Bqds9CS1BddvF7N1qJZc49VlyxYDcxdhAuBvf7wX3/vNUNVvLLfgycnU4aZKJoqmSON70WCjLLDNuG/MbMYhUWFMuGuUKCGIyATTJVHtLZmixclhrvKWm5nwfiOqSMgb9pIyX7f3JdGbjuLoRAFdCQ0RtcKa9v5GCDAPjhhasemUEr//WSLCKfGM9LHJol/bZwCGZ8pIx5Sqdi2HcUQUCRFVnDNNosi72Y1aMA63B1zE273pCBjjKJkO/uKN2/GWV6xZ8LO02LXj2vu0LarMe6xsK7/x6YdEJK3IBJI7BIQQgEiCSGjafNl0DJaa+LZSJnQtN0JDvYTwDJgnR5gpGP6i5d1c3UkNl27unPe2F3thCZJrBqdKKJqOb6A9EALkDdEnG/yN5RQ8adU5afZAt0UV6JYgXClyRQmrFsT7P/cEeBGdN7dZlQimSlbD74raLfNTtFFFMJyXskXNOy/Hp4qiJuwS23pSQkM7UzBACNCT1JApGOAQkW4zUNeBmc1IUwLEVBkbO2J4w45e3Puro0hEFKSjCoqmUyUZKlEOmwnhk0zBdNutOBgnkCjQnVR9p2K6ZFYZ6UbOgnibw3IY2qMqdJuhI6EuOCu12I5mo/t0c3ccHXEVL57ItzxWdi7sHclhcLIIQggoap49iHNrOQ7K1vwj9ZWGlaBpcKochdBQLyGCBiyiSEhost/iI1MKDo7JgjlvAzbXwjKa1fEPD76ID9oMnQmt5Zvp8q1dePvF6/EPDx70DZMHmYrxgxbjcBhDXq/UXJdL8KRV52S2BzquyX7a1nZYU0PkcEB2TxkB0JUQ19BLJ+8bzfnveQY5uC3xb3dUaEJDtmwvGfM1eF464hoSmoKJvAHddjA0VUJbTMWm7gSOTxVddjaBQgk4Z3XZBMmNuJtxzQJmxU3/E0wVDfzWWT149qVp7B/NIxWplgwFATgIVImAEmGsve8DHIQTTORNAAQxlWI8r/u/NRfL4URWB3GPZ6FO0GI6ms0kWr0yEOPMz661OlbW224jAzFVMsG44B14WS8PLlsEjIlz7dXfVyNWwoSuU+kohIZ6CVFrwAghVfN/GePI6fNPh862sBRNByXTwZ6hGdz67efmxfzcNZDBPbteEim5mhSp49alZbcm2B5X/cWrmXiEV+MumjY45ye1UMxHJvNjP3ih6QP9tlevR1SRULL4nH3CDKgQc2yGRESwWcfzhm/IFLceTIiI7oJblCj1eQhL1aLW6LxEFAnJiIyy6WCiYGJ9Rwzffu+leM/Xfo09w1mIJZxAliisQPsTCfxJG6TIg0baw0zRApUIdh2e9DMywzM6dItBooLZbduuE0MAh1S+LwmfAZQAJcPGoGlDlSUwJl6TKJnzGjkcGMuVcdnmrjoniDGOPcNZPDc4A06AV65vw3lr03XXYLEcTa/rISjRaud0dCcFK70vRXF8qiSyMq7x9u4jVaLoTWmIq3LdWNnZDERHTEVUoTBt6raliXXG4Rx2YPsl08anHjyAW163dUVwReaDlTCb+1Q7CidLAA0xC4IGrBEMh0EmwFTBxCMHJ7BnKAvWQttMs4XFm1BkOqJemozIiGuyfzPtGsg03ab3MBQNG5QQvy/WAwdg2QxwJSAlIo7r2cFpTBYM9KQimCqa8Lr9CoaNY5NFvDRVxFhOR1638akHX5x1H2ZDq1HPpx866D/QEUUCpcJw9aU0FAwHD+49gbgmteQ0eJdiU1cc565Jo2TYGC8YKFvi/CoUbhuW+FOTKeTAQiG7IeH2/uSSPcjNzgshBDFNRk9Kw3hOx4vjBdx81Ra/79h2GAg4JClIkqsY57VtUUikskA0MtKAcGZsh+O+J44BAO64/jysa4+Kfmq74gwpEoEiV2rZAJCKKmK0pcPB3N/WLQcgYv8JAVpZdh0GnLu2XrznLZ9/HDfc/QQ+/uO9+MSP9uIP/u0JvOXzj9fdg608p3NF7N5C/sJw1pdopYSgbDEMT5dRMGwQQpCKKgAXbHzZbeED57Ac0Xc/XTarfsvb7v7RHOKajJ6kVvVMZ8smtvYmXalVwGIcpuPAtKuzJd0JzSd2LvQZPFWYT8ZjKVDrKDRaV+565HBLa/dCERrqJYRH0JouWahtV+ecYzxnoGwzfOrBA/jQt5/HTV/7Nd59z9NzPkiNFpbghCKJCOanKkkt30zewyAWctF3WwsvRUcIUDRt5Mo2Pv/zAXz4u7txfKqEomljcKqE0WwZx6eKKBkOHIdDdtWeDozN7TA0QytRT9lyMDhZnPWBPpEtoycVgWkzUMxtCGSJ4OP/1w7c9ycX4+53XoRP/8EFeM8Vm0QLEkSbkndtCREkMpmKB+udl52Bu995Ee698eIl87ZbOS+eQ2Uxjve+djPO6k0AhMC0OZwGEatCCSaLgiRHXMejWQraez1TMHDnT/fj4jM6cONrNiERkSFJBBIBNIWKUg+vZosXDQuOw/z6vUwrrV2McV9RrRV886lB/9nZNZDBrd9+DntHcrDdyFaWCBzG/JnWwXtwrud0pmRhS0+iadkiuJCnozIA8fxRIlLyjvtscs6RjMggRJxfEXVTNysj7t+xrI7OhEhtt2Ig7n70CG66cjM64goiiiwyYTX+hipRaMtoVBYbrdzj1hLOEjjVjgIQGuolhUfQSmgSxnIiEmOMC4MyVUbJTQk38pRnM2aNFhbdEq0sEoXfOuSxaFu5mbyHIanJkChpSjTyXp8smODgSMfEvnfEVUju3OFMwYTN3NQxAToT4v2FLBSMcewZyuJopggAoh+9AQyH+YIesz3QNgeu2dGHmCa31OX9ivVpXLGt22ezKpTgmaNTIo3rkqMMm8FymBjxyBkcBqRiCj589Vk4b119qnW245xPZgWYOxqcLpu+Q/Whbz+Pnb8YAEDQm9RAafXxEwiD6QAwbduto4pU62xQpMpc6Df+06P49IMHUDIcWA73NcMdV1o0CNMRUbTXliRLFJQSaDIJ1LBbx57hLD7yvd2444H9mCqa4nhkYQQlIgwiIfBnWnvneLbndCxnIK5SXLOjD48NZBpem+BCrkiS3x0AiGdPpgSGLRQITdcxAYC6mkPN8bZqINJRFXdcfx42dkbrhGy8caXD02UUTWdJjcpC7+G50BZVwMExXTJRNp06Z2qpZwmcakcBCGvUSw5PCGDnLwdwYCwPy+Ei4iJAXJOwvj0275pLI/lDy6tHMQ6JiuELwX7euepscy34QViOIMOsbYsiqohbyLa4kHt0nyGJVNp2poomoqog082HmBOszZk2Q063MVM2sbYtimSkkrr2op71HTGcyJbnHA5yxdYuUAL8fz89MOex7h7K4vFDE7hiW3c1aSumYrIozqWXafAWSYkA73/dFshya37wyZBUdqxJYXN3HC8M55B2U8le73RetzCWFUpl6ZgMTZIwU7Z8IpxECJwGropEAMup2A3WpE7sG0JCYHMGi3EcnSyiPx1FQpMwU7ar1MoagbltWxIqoy87ExrGc8a81NPyug2JAAXdwgh0gPPAeEx3f4noLQ/OtPbuwWaCHf1pDQCw8xcDTa9NcCEnVDjJuuWASOKYGBOpfctxkNVtEIjt5nRb9FG7feZRVUY6qvgE0/nUzl+7tQvpqIqoKqFsOJBlCsHjEzKyFhNR/Yb22JJMslsqopVX98/rtl/312Tq1/2XY5bAShg6FEbUy4aKEIbDhCRnQpt7HnUzeAvL9v4kSoaNrG4BnEOVJX8aFwdH2R2pmdOtWW8mL0rPFEzRC+wydOuPQqArofnGkoNjIi9afrw1RXJTfxQi5TieE6m/Vr3P2tpcbyqC7qQKh3EMTpUwVTSrop6EJuFDV5+Jrb1JTBWFCpc3SpS76Wkvhbm9L4kf7x4BmSPQlalwSj790EHYNqtKQ6aiCpoFmqmogh1rWmPxz1WDnKtM8OSRSWTLFvKGjcHpEo5NFnE0U0SmoGN4pgyg4lARCmTLlquZBn9IhnceOLwaZ3XKWdRbq39XoQSaQl2p0oqT4jBgLKsjp7c2GhPw2Pein1qTJXTEVaxtj0KmaHqOayEa4kTblpjShYbX13vJcurvwcu3duHeGysljlt+aytyuo3RrD7rtQku5J6OPwAYbpZLdEpwDM+UQSB66ttjKs7oimFjRxzr2qPY0BFDb0qDRMXaMFkw5lU73zuSw5GJAjpiKiTJ08UTRxuM6nOGXbcOnGwkfLL38FzbPTCWQ1dCg0xE5qZsOhieLmGyaGAsp0OVCC7fItpElyKlf7KlkcVAGFEvMRqxBadLJrK6hfGcDlWmC55HHVQCyhQN/NN/HsLQdAlxVapSPvL6oVNRBdly421SSnDTlZvxv7/1G1fOUaQkHc59gY/OhAoCYDxvIKZWPEvdZDBsR0w6cltOBImosuCXTDHmLqbKc3qfzVieHXHREzw8U0amYAiRB4lgXXsU1+zoQzqq4rVbO/HMsSlMu+fOW6Q0maIjruLmq7bg3399HPtG87OeW3FOKLgjBCh+tHvUT0OCAGPZckPhEFUSZYNWWKh1E7oIfEnJdERGVrdm3U7w3upLRTBTEjrYJdNB2RLXoz9dyT5410mWRFTppz/mWNs8XkIVSMUQ1Pbbc9Qol80BxgHLFuIfXiZIkSh6khFctLEdP94zOmca3Ktt1+5D7X57H1Gk+nsw2ALVFlXwxRfGUGyBaRwcipKOKMI5bLafRPAevOgsqkooGBwncpVnFQD+8b8O4UNXn9nyVLrHBjKwHI62mILpUiWi9421ez5yZRsXrE/7RuVkI+GlYmQ32q4qU9F2aNmwHI6JnIGYJoFzjq88fhRfe+LYkrRLeRnM27+3G0PTZURVCVFFlDiyZXtZhg6FhnoJ0ewmjqkyZCq8w4m8gbgmVaXo5pNKCSoBaRLFR7+/B8enSygaIpKkbh+rRAgYAz72gxcaMpB3DWRw96NHfClIm4m5wpQSxFQZ3UkNCU3GTMn0tZ49WI67wNDK615PZ7AXdjynI6YqVQtFI8xWm0tGFGzoIMiWLbzpvD48P5TFiWwZX3n8KL702BEUTdtfjZm7WjtMtE69+fx+XLq5E3/3wH4wN2vQLK0LiMVQKJdxDM+U/DTkVNFEuYlQiulwONz2J2vNlt6vn9BVLSkpJnTlGm6n0b3VHlegm0wwiIsmTJu55CYBb5AIoaiKkOeyqa7vVdWyZzkc4OL+CKaovXvDu/6t2mtFFk5FXJNQMmxkCgbO6IpjsmgiockwHQbDat73DgIQXv17lsOazrQ+u686VVprsDiEjGxXQmupt/rKbV145tiUkNgNnAtKxGSxnqSG9piCsZwBh4t6a18q4gvDMM7FNSGAJkk4PlXCx37wAt5xyQYcnyrNOZXOi74th7uT+cq+wy3U6IQcbjzwncVoOVoqsaNG201oMuKaBN1kmC4ZmC5ZABcO/HK0S6Wi4vrldCF0JFOKs/oSSzoZz0OY+l5CNLuJveH0AKBbNnSzmr290FTK5Vu78MnrzgXx9ZPFb0YVCevaY9jQEW1I5gqmrrqTGuKq5C/klAjVKK8eVLYcJKMKSm5KuWDYGM+bcLhYvINZutpF1WaA6Ti46crNs3qfc9XmIrIEy+H42d4xDE2XIEsUUVXoJxuW0N3mXBBpVEmwiTkH/s9vhvGNp17CeM6ARMUCOlv6mzFAkYT3vLYt5g9XmSrOnulw3P74TNGY9XPecZqOaOHx2r681jjDdjBTMvH4wETdd5uNT42qElJRFe0xFYwJY+PBmwHtSs4LQzLrHlbAAT+l6sETv1FqrhPnFWW3ZqdXlSk644roQYcopTDOcXi8iKOTQl3tWKaIX780jWREwdbuBDZ3x9GVaO681hLjOBcthQ5jcLgg/HEOdMRV3PK6rf492Ch16y384zkdBaM+jR8s4ewayOAbTw1ClSiUAC/BI8QlIzJiquw6UyokIvrvx3I6xrK66xALJ0giFL3pCPrTERQMB48eyuCT153rl7jGCwZKhl3X8hdMz8ZVUf6KKBIY5+454EhFFXzqrWKC22K1HC0F0YoxjmcHp1E0hA5/MN1MQBBRKXTXaWtzxaSWsl3q8UMT+PPvPI+XJkvoTqrY2BFDXyqCmCbNq8RzMggj6iVE7U3sCYDYjCEVUWDYDLbDUTJtaHLz+c3zka1LR1VEZYpkW7RuMAOAOg+3UWTWk4q48o9C53t0RkdHnKFkOWiLKnjHJRvw9SdfwtFM0TWKzclGQWKrJlPEVRnp6OyZgrnIG7rtoGw6sBmD43C/dlSb+rSZiFIEm1iQ3e751TEAohZq2Mwd6tB4/ynhUGWRCnzz+f343m+GsGc4C7NJNB2Ewzhmio0lRmuPUxCnxDZt5smRVI7jwb0ncNOV1am1uRbIlCbjBCXIlS2/dzqiUmiyhLJpi8hNoUIUY+7DcXeGQJYqZEJCgN5UBCXDgmfLvDPJUR/hBmE7DHldcBbUCEXZFE4Jh3DEupMaLIchZ+h+iSimUmTLTXbNY1m7+xV3x18OTZdhOd7ozfoI6GSzXm1RBZ9+6EUUDBsbOmLI6xaGpsVOMvf4Z0qWO6ucojOugVIxSvXBvWPYMzQDEFEyiioVkhSAKlb3vTdePOfwnVqC6YaOqJgAV7YQ12T8w1vPxxXbugEsXiS82EQrL7NxYDSPvGGhaNqI1JwXv9RGSJ2TuNiSxY8fmsCffes3yJUtty/e8clsHXF1WcRWgNBQLymCN7FtCdalp/VN3BqfR1gaLxgNx8LNt4Y0VRKtUR1xpeGNU1v/bpZiWtsexWi27EeoozkdCqVY3x4FIKKEwalylSFutChTiEWkJ6mhLaZgomDO6V3XDgiprc1NFkzR7mPMbWEYh1/LJoQgUzCgyRLaYqo/GEGuSd8CQqxEU4Qwys1XCQb3zVdtwa3ffm7WdK53HighaI/NLqqyY00KPakIRrN61XmsdXAGJ+sXnbkWSJNxpCIyVFmqSpumowpKbnmgI67CcThO5GeP/CsHx8GZMCjeojVdsoRISQPMdp4Yh+sgMex82yvxj/85AMth6E5oiKoSCCEom45vLIenxQStZpUKz0B7GuVbepL47k2XYe9oblZlsrmyXmXT8bNeUbUyVc6rDwOo+r4iSX7rXu15KFtiylcqIuOKrV04qzeB//v+5xCRhQOVjsmgpGJ4gs9qK8MumjHXz1/fVrdeBB29YADhOfat8mTmelbnw8gOpuLbYuI+1S3BtxieLvskWctx4DAxRjWi1DuqiylZ/OHv7kaubFXNePdEbNa2RxfVKZgNoaFeQng38fPHs9AtW+hHU+ILilg2gyoT/O/f3ooNnfE6T3muGtInrzsX6aha5WXP18OdLTJzApFTTzKChCZGQ/79z15ERBHSmV5607NzQY1wDrHg9aWjiKuiNWi2UZkeGkUHwdqcWAhdxnLgt2aDaIsT574npeFEzsCaNg0nciZMh/kLvAfbTeWnAgpml27uxO+/ch3+7dHDTclS3stxTUZnQpt1nygleMM5vXju+Ezd971jIwTIGw7GCzr2DMG/1tv7knMukOesSeOmKzfj7kePVC3c3qI5WTBdpnIFXs90bZaBQNwPEhXXU6IiUtRkipmyeM9jJ88n42gzjqeOTmM8p6PXTcF68Ixl0RXOaQYCUePmTAz+0BSKD119JmSZ4oL1bbhgfVvT7za7/wkh6E5GMDwtuAnNsl4zZUs40FQ4FqbLMahsxysFEMhUTLJyODBdMvDPPx9AybBRMsS9MFOWfC4IsLC2H49g2kg6NQhvnZgpm8iWLT+AAATZLanJUCQ652/P9ay2SrSaNbPnli7GczpoOoKsbosBO7H6rpmFnrdm+1M0hJ6AKNEQV2sAS97uVovQUC8hPCb1n973az8a9h5cxoTRjigSHtp3Ave8+9XYP5bHYwMZfyGejU05OFXGn33rN4gpUlWkfdOVm+fl4TacQx1ot5JlkZZLaDIiChUPDatIQ8pERKocQklKIiIepISAQRh4ADiaKfpM5E89eKBuVGYtvHr7px86iMHJIhiAqExxdl8SxzIFYbCBeTGWJEoQUyT80cUb8C8/P4ThGd1t3ao2LhUSEDA4VcJHv78H77hkAx49lMG+kdychkiiwHlrZyfMeViTjvoDFYAACc8lk3EI9bC//+mLKOhW1bW+clvXnESjy7d2+a0rQYcOAL759CC+9dQgCobtX89mZQCvz9fjMByfLoExkd3w9jfYQz/XKE0CQJEAiwEP7B5taiw74yoKRrnqe7Wb5hCsceKm8//8DWf6KV5g9tLRbI5tQpPRldSQyZsNs16Xbu7ED58bgW7ZOJKxfLJe1f3BvT84GBP3IGMct337eRiWYODbTDhLeiByjKvSgvqDvaEg//70IMZyOsAFH6A2C7djTQqdCdHWRYg4115WyWYcumUirklNu0SCaBbJz2c2+GyZPY/pXbYcZMsWzl2TRrZsYjRruITPhUfxc+1POqqgbFUInoDXSYKm7W5LgdBQLzHSURVxVQaBqKnaDvdHJXYnNUiUYN9IFm+9+wmM53R/Ie5JRXB8qoiOeD3rtGg6KFs2HCaUxNpiCvK6jd3HZ/Dh7+7G/7z8jJaYokDj1JVXA6JuCi+qiBSTp6zkyTECJMDuFiP1bLeVizHxABk2w2TRcBmoBGvaolAlOic78/FDE76RttwHvzcdxTU7evG5h7P+53ziUgsgBNjam8QZnbHgq6hd+j0FK8vhsB0HtmPgMw8fRFyVUDKF9OhsSfeuuIpbXtdau0Z7TIEkESG1KhOABzSuCWBaQixjLFtGbypSlVU5PlXyHYjZFshGadNdAxl86bEjKBg2epIRjOf0uglgQVBCfPLX8ekSCrrts/k9VriHVuZdi+8JidFs2YQiSQ2NZW0LsXe/eRfdcw7iqoStvUl86OpqIz1X6Wiu1K1pc1y8qR0fvuZszJQt39A/eWQS777naewbySFviNS/5+A13F+IZz6uShh3Sw0SJb4BB+HufcAwltUR14RA0HzafnYNZHDnT/dj32jeHawj2hI1ZfbnjbFgI2UFZdPBX31/D+78vfPnNLbBVtGFzolv5Kx5TO+S4WCyaOIDv7UN77xsI548MnnSUXwr+zPfdrelQmiolxhTJROUEGzqisG0eaUOpIq2kVzZwnTJguUUqhbioxMF5A0bCU2pSgd6mt6Mi7S05TAMTpX9Hsy8IcZP3nLVZjw2MDmnh9sodWV67VZEsFC7kxHX4xYRgzDIIt0o0n7VQxQ6YgqmSkJYI1PQwTgQc8k9Xlpvth7LLz56GJ95+CBMm0HM2QUcieLIRBH/+ouBulR1q5nWmCr7qWCHcZzZk4BuMxyfKleJSthMtPXIbruLx8buiqvI6TYUmTZV3FIkgg/89pktt2t0JjSkIgqyZcuNuCrRqW0zf4JXXJX81qpgj+qjhzJ+NqbVBbJRmlGRCI5PlaqMbFShSEUUFAwRzYxkdXTFhegMC0QYC4XtcMRUCRIlbjlCRzqiuDOsxTPinWMCERkGIxsRvQrJ1utfuQ4ff8uOquNutf2ocv/rfn8s554okYxbXre1Kn0e3G7JdHzHjaPxxLGelIakpsDhoiefw2Xbu16m/z1XaMawHZzVl8BfXHO2fx/ZNsOPdo9ieKaEtW0xvPn8/irlu10DGdz+/T0YmSkL4SN3NJluM0zkTaxpi/hsaM+gThZMtAcU9mrBOJApzN7LH0QrdfRmmC2zQSC00+OqhFdtbAelZFGi+Fb2Zz7tbkuJ0FAvMYIXPDjiEnAHc7jedXdC8w1yhEroSmjIu6IlnpA/UNH09lLLk0XTNZ4ERCJgjCFbtvCVXS/h0289v66G3eiGqr3phQY5oFCKzqSKuEui8dp7GIffu5kpmLAYd1ugRJxkOBxr26J407n9uP/XxxFTJaRjSp2cYyMixuOHJvCZhw/CsBgUWSibcYi6k80YbCaGSUiE+GzzVgw1AXDr72xDOqr6KTZKxdYdzqo+x7iogUuuIpfFxOt53YbjcDAisiKeahbjQGdCRTIio6A7WN9RidjnYuzvWJPCOWtS2D00A9ut83qSkhIVkTYHMFEwkSma0ORKHdM7fz/aPYqOhNpyFNMozShTobNN3HPKONAZV9EWU9Gd0pAtWSiZDt528QZ8/ucD7hhKode9UHAAqagMAoKLN3XgW08P+ql0EDez4V5dr53OAffbrILXPRGVq47bc0byuoW2qOp/J6JQ9KW0Kifx0s2deP3ZPbj/meOuhr2IjFMR0eEQXPSrBnC4DpbnuAVHhnqglCCpKYioFEcnyvB8Owavz7/yWYdX8jvZsuVrEnzx0cP4/C8PI1+2wCCM/Md/vBfvf90WvPfKLf4+Zd3uB1mifoufV0/NFAz0piL+8+ZFjMVA61nwrvF2y3IYBk7kl5wstRBS2slG8a3vj+an4A3bAXMqAlJeu9tSIzTUS4zZbsCy6cCwHWiyhKhW7UVGNUloBrutSDE3ErWZaJkKRpOSyxwPLl4TeR1//7MD+OH7r2jpxvVu+m8+PYhvPT2IopmHyRgm8gZyZQvdyQjiqgRVoiiZDmKqhI6ECk2RfDa7zUTq6tw1adzyui2wGMd3nh1CKlJtpD3UsjMZ4/j0Qy/CcGcZE5epRkGgUAj2vBfNoXKsEq1PkcoEIJS4fZjAjjVJvOOSjb6Ck5dis0Xez0dlgRKymCRwnrN6oAepZkUWhp1CkRjaogr2DGXx+EAGD+4dqypp1NYKgxmNgmGjTVYE09V0ULK8tiJB8OG8uo7JOMdEwcDf/niv+9utqUo1SjPaLvcAvJLWH80ZmHGvfTIio2DY2D2U9dveWuhSA9CcRiBRgrLJsL4jip/vPyGmmZGKATNcq6a6ji7nTsO0OgHwk+eH8dqtXf5x7x3JYd9IFmWTIaeXqkRkUlEZUYXi8HgB33x6EPc/MyjkJ2tqywXDwpceP4oda9JV2/WcHM/4EyruUaoIxTfHLfuAc3DGUTAs6LZ4buaCtwtHMyX8yb3P4Jy+FPYMZ10iKiBDpMuzJQt//7MXAQCXbu7C4fECYq4iYTDTEayncg6/p9mrqXqZpLrsiLsjjDGUbbbkZKmFktJmi+IbOckAWjLs8213W2qEhnqJMdsNOOFGDz0prc6QEYh04NBUCRMFEz2UQJMopotW1WLFAb8PtsojZuKG/PiP9uGtF65rydN88sikX7fsTog5xo7DUXIcDFlFdKciYhIRFXVq3WKIKRJ6UxFMFkxoMsUHfnsb3n7xBlBKsGcoOy8G+jefFgsmR0UZTUguijFP3kLq1QK5a1QcVm0MqMtu8jINHXEVH33TOVUKTt4+CcJWY9RGbbNhumTBtB1s7k7gUw8ewP7RnFBOghjS0JPSmtbmPeLch7+7GyMzet1veqxhQgDi9jELNSsxiCWuyUhFlJaVmRqlGWvnF3vnsWyJdC0lgpfwxOHJhineWgTr+M0+yhj3hX+mS5YvVapQkQ/mgE9cnO0346qEnO5g5y8H/BTt4wMZTJcs3zgzl+xoOaLdhxJhnD790IvI61bdsTN3xyfyYnyn5/BWtzUFWN3E5WkQ8d2gI3MiZ4BS0vK9BIj72bQ5nhuq8DFsd6eI/2+Oz//yMLZ0J8Tku4hctT/BbXmpfO95E62BGjIFtzUvUEz36v7eNaTAkpOlgMUhpXloxE3odMVyJgtmS62ujQYqKZJwDG553dZliaQ9hMpky4DaARqeutDm7jja3NpZIygSRVtMxebuOEqGjWOTRTF8owmCC4GXWvv6U8fwv+57Zs4518GUXkKTkdMtcLdvkEEsOuM5A+evS+Ev33gWzl/X5h9L2XRw3ro0Pve2V+CPL91YR1RrRcx+10AG//Jfh2C7q7G3znh90FYgZKaUoDcdQUyT/RnGMiXY3BXDjv4kOuIq4m5q+JJNHfjcDa9oqODEOa8SgzlZFE2GsWwZ+0dzKJuuk0EJLIdhdEaQtRopJ+0ayOD/+eELVf3UQTgcMG1H9I67KlMiuyDelyiZlzJT8BwwzlAy7Dq1NUrgp/5t9/coAZLa4i0ZHMDFmzuQyQuyoeOWW2RKQSjxpUjnMnAFd/DM00en8c2nB8EYx4N7xwDA732tnW0tyhtAtmT52RjXv6veQQ68OFbAnmFhMKucHFdARmR5RCRtMwaHV7oivM04Ta7FbOemlfdzZQsvDOegSATUndwlZIC9shCH457HvGFjc3fCd9r/yHWo/UPl1cIx1L3UGzrjS06W8lA7GGUh89wbKc0RQrDXleMV7abzGRxSGajkjTtZboQR9TKhUT1le18SN977zBy9sCnc8+5XY89IFn/8padco+QpWM0NzkVEOlek5aX0NJliZEaHw0UdnHrMVC40nK/Z0Yd3XnYG3nPF5pZSSNfs6MPBsTyGpsvoTKiIyFJdOgsQQyzEwAjiL6qEVNStgseqSmLARkdchW4ylEzRXvS5t70S561Nz0vBKarQpspqC0HJdNCXiiKnl0TdlxBQN5qbyBuId8WqavN53cJHvrcbx6dmb0FyOOA0GRc5MqNjbTtBQpNbUmbyzsGt334OB08UwBoIiRCI6xAUgrEYMF6YXW2tGbwr4JcriNgPwYlwYLkjDMXvMN9haxUOB5jD8C8/PwRA6MprsuQ7OC3tn7uTXlTKAUiSKAv85vgMLljfVle7TGgyiqYNw57f/jYrB7QCL/jlcNXPCPf3qSuhYmRGd9Xjqq9fybCRLZt48sgkLt/ahbdfvAH3PzOIfaO5qtKR15roBHrS5yInLmad+GRIaY2IkhzcnxoHIur/7a706Gyk1mZkxANjS6cn3gyhoV5GNLoBW6nLyDLFsUwJuiUMmYg4+Kxzfj0wLrxuTaGYLJj4+58dwAffcCa64lrVAzVVEkMcypZT6QdFZbgCIBaGLz12FOevEwIKsz1MwdSTbjPoloPjU2LyTFyVqtJZe4ayODxeQFdCg53TwZioRTZqvSIE6EtXSgVRVYImU4wXRD11vgpO+9xRol5/68mabImKiWNVfZdu65phO9BNBk0WtflM0cBXHj+KqaLl/y6Zxwouate04gS4MpeaRDHjMDw7ON3S4tnIjjnzyfs32iaquQO1m6JETMqayJt+1gaMu2zahf0mAVAyHHzx0SMoWw5SERkn8rPXhb3THbzPg8fg90FzMQpyqmTimh19GJwq+cNvZpNKDTLUm/12s+/N6l8Evkx4kOfgIBmRMVU0q7ZNILoxRrNGlZG5/drtuP17uzFZNIUYi//si1nj171iLdJRtalA0VLNoV4oGhElg1PjAFGv1y3mK+A1cmyXairYQhEa6lOMVusywzMlMAiSFABX55ZUpdiaIavbgC7+/vxQFjd/7Vl0xNWqB6rDHd9YtpyqWrBnOLxfGZwq4T33PoPt/amq/Qt61cenSvjiY0dQdD3R9pgKw3GQcevYt/zWVr+ODVTITYLRLNSIwJivlRxEbzICiVDkdctv4TkZBacfPjeCv/3xXsRUSbA65xnJ1YO7GQERpUqotK5x5pLXHFGHnSlaODxecFtp/K83BSXiunv9ztRVSwo6AVFVwnTZRK5s4/M/HwCAusXTW4Rsh6EzpmA8v/hEIZmKmqDX1VBr99vjCiKyhKJuIuEONzgJAjkAYVyKpo28qybl/TfbFZ3L1WVMDCP54W+G8cVHj/jGqCOuYrIgJGgpFVkTAKj1nWvrxf7rLR9VYwRT1OeuTfnryB0P7Me+0VzV9r3KWk53sKZNqWrTunxrF+78vfP99Uc46uJiKRLBf+0fx6MHJxoa38WYvrWYCA7ziCiSL4YSnBoHNwAQ2vqCn9FIcjRo8AH4swU8idXlkg71EBrqFYBW2gzWtsUEuYNXRBUkSupqb61AtxlM26l6oBgXA9mD0Uwwogi+5g2av/17u3Hn750PAP6DbtoMOd0Gh2jR8lrOolTG2jaK4Rkd33p6UETkru5ysO5XUSMSTHLGAe4aJk0RBnqyaPgLoCqJfufz17XNu45GKcFbXrFGDNtw2cwni5LhoGzpcBjggMOGGKfpTeqSCPFbTdpjCoqGA92utMjMGkS5RCWZEkiuk0Ypr3IC8roQzJAoQTomQ3OFRPaN5PDn33ke77psI/pSUbwwNIO8YdcZlsUEJcSfjkVcch+HqOXmdQdTRUv8vUWp8VYQ7IaY79X0MjjB73mR9vHpkpiHTgnyho2jmSJKpoPOuApJIsiVbRh2c1ejNkImEAaU88YkuVarMcmIjG5X/Y9xLhTjan+HUJfcVt+mdd66dNX68/jABO574iWYtjPr+MiVFnHONsyjamocKux/D40cfX+ync3EzIPAjAZvuMp8p4KdDEJDvUIwV8r2zef34+M/3otsyQIlDJRQXwhgvkQVQLBsz+pNYLxg4c6f7hcRTYtjlGZKFiSJoGja+Oj3d0O3GEqmg3RUQTIiY6YsiFrB2mnB7QnXLRv7R62qqPzSzZ1VLWwJTUZcjUO3BIksW7bQFpMxNK3DYIJxLlGxKJdMIUt65bauBS0Ifr32/ucwswilapujauXlgF8vjCgSsrrlK04dyRRRMG3wFq8fZ0BUo74s6/B0GZbbKiUieeYP2OiIqQAnIBSwLQ7dcjBdMvHZhw9CpqTpPO3FgEJF1D9VNP0MgEf6M902QtNx4LevLx5FwMdc6nF1nyeoy+BIVDhWEUVCfzqKoun4i7Y3t32yaLoKY83LFo1KOBwi+vb68RsZa49BDt74FEVk4tfNvQESed2GTNz7EN79J0aRypTUtWkBlWzYZMHAg3tPwLSd6t5ztb73fKnmUC8Ecw3zWNMeqZoaF1Ukf5hHsx7tjpgKxhlGsiYYr8xo4KgerrIcbHggZH2vGsgyxftftwUSJb7Cme2wBRlpQCwMOd1BOirjxbECsiXLNwBzQZBNhINwbLKMsZyBkulgLKdjNCdU02RJsHYn8gYKhoXh6TJ0yxHkKkKqWpWePDKJm6/agoQmJj152rogQi41HZWRjCiIqRJirkKX7S744jUZjx7KLGj+LGMcyYiCN57bVyf/uJjgEDXl7f0p3HH9ebh0cyd+9sKY3yYkz/Hjfi3VPUYv8xCRqd+3m9dt/7xkCiZemixiYLyA41Ml6DbzMzBLaaQBwHZZxrrN/P5602IwA1EJd8mQhLgpyUVGq0R+j90e12TBnHb/nY4oOG9tGsmIjN5UBEXTcWeGC5Kld72EwRXx+2x+bu2d6fM+OKDJBElNguI6oMTdL1WW0BaRq75LURHasRlw5TaRWvYGSICjroTgGWu43Ilgm9augQzefc/TuOlrv8at334Ou4dmMF2ycGyqiKHpMl6aKuJYpoSi6VQZ36WYQ70Q1Eb2UUVGj9tGCi5aPCdyBlLueeRcCJV452EsZzTs0d7el4TjrjOyP7ueuNcefpfC9r7kkh6fhzCiPkVYCFPyvVcKhrSnUnSy5VTLEVKZNmOIqSpUWaqbItUIkkR9xqn/mlvQttx0tTeAwLAcjGUN33iL6IIjpsroUCopsntvvLhprf6aHX3Y+YsBJCMKZkom4JPcxA4kIxIOjOZx35Mv4cIN7S2zToNEGKEEtdAz2RqiioQbLz8DyYiCPcNZHJkooCcZwUTegMPqJ3h5SEdkaIqEqaLp9zWvbY9CkSgiioRUVMHZvQk8NpDxF3XmkrIsd4PCCLTGaThZcO5Gg7yS8vX6ceH+qSgiJS9RMVBjscF4dVTdKNiViNAwAAf+4o3b0R5TMF2y0BZX0BXXkCka+Ivv7IZCCUazZThc3JOEEHACkEDZqVZwZzZIbnTmMdvLFsf6dhWqTJFxtRU6EipKpoNMwfCleb1ebUKAiFvyefRQBhdv6hQdGwpFTm9woKi0iBFK/HbKbNnEx37wgl9jdligl56LoSmUEF9kp78tUiWYsphzqBeKVod5RFWpampcs7HC3lz7F0ZyYkSve50kyvx72VMtlAjB/rF8WKM+XdGIKbm5O4E3ntuH9R2xWQ33e6/cghsv34SdvzyMLzx2GHFVTLUaninPu96oSNTXsY4okj/FZzYQNwK0an/M8zYlAsfmsBiHSjgYxMMsuyIWNuP+kI/aFFmzWv1jAxkUTQclw3bZxBQy8UQcGIozOggBPvfQQcQ1qSXWaTBd5qmtLQWCBmK8YOJ///tzSEVktMdVFA0H69qjcJin317/fZUCJctB0XTAIerRDuMYmSmjO6HhnDUpXLG1C5/7z4P1RKbA3z2FtuWClyVIRxUUdFuojLnXjFIROXJLRCWNos3F2FWPyY8G2yMQsq+WA2zvT+Itr1gDAH4KeGC8gJmSCQ6OnC7GQMqukRbfJ1V1z/nse20WjAMYz+vY2pPEuvYoxnIG+tMRXP/Kdfi7n+wTgjZRGYZVPStAtxgOjxfw3OCMO4rTmfX3bQ7InCMdrWjee5EoCJCbrn4GHCYGhXgtk+M5A+0xxX8uF2sOtYdg8NIeVbC9P+Ur1XFU7l+h8S6cpOEZUYpIRUilf5wDEZliXXsEJZNhumTif152Bn7vVevAwXFgLI/pkoV0VMG2ngQIAY5lir5kKwC8eEIQ8nrTEcwULb9UQ4hYK7uSGkqmE9aoT0foloNHXhzHJ3+yH0XTRltURSpCkdUtPHkkg12HM0ioMmKahM3dCbz3tZtw2RZhbILeNCHAeevSiMiSS2YRD+2JebByJAKkIhJGsgYUiUK3HWTy5pyLjOdR1i5QXqqaEgpZEn2wtgN4GpxeipBCpBl1izUcUN+oVt8WFbKajHMoMvVbsxh4pQeaAx0JBTKdu2c8mC7rTWk4MlFaijKpf9xBWI6DmKZheKaMgmnjRK6MnO4IbWtfkYv7RtdigCp79TEhniJRsRB9+Jqz8ebz+/HWu5+AaTMo1O0nbmD8vD745QLjQvpzpmjC4ajKFpgOh+m4RqFJ9FeLzriKZFTG0FR5VtJfsAfaVaBtaKQJRHmgO6nh5qu24Mkjk367Xk63Ku1IHJh2F38pwM63Wb2Sm7fvlIi2Oc5FH3MtiazR3uu2qOl3JjS0xRQcmSiioNuQqBiMQglBVAWCswK8Z4e7u2XYzpxtXRs7Yvjb685DMqJURaJl04FdO+zGPY8UBJQInkN3MoGzehNwOMd7r9jkC/WkA62l2ZKFuCbh3ZdtRN6wA6NkeZXRZYHXf31sCl9/ahCDmcq0vPWdcbz94vV45Yb25gfkZm/KluOr3NUiKlNs7UlCd8l+m7ri2OS+x5q0IaYjKhRKIBPRvaAHApq4JomhRJQtW406NNTLiJJh4wuPHUXBsNGVUEFAUDBtZPK6nzozHAdpScb+0Rw+9oMXcNsbzmx4oxqWeKiKpgNNnv8CnIzIGM2JmbM9SQWHJwRb1CNpzYZG6VMOBs7F/GTCub8gSUSkBW13XjAjYobxVFG0aqWiChRKMFUw8cjBiabZBH/xcR0CDnc4Q+BlCjKniAFQnS4zrIDRQAv9qycJhwHgBGvbIjh4ooDJouWz172oRJD6KjvhsaYJxOcsxqDbDG1xBfvHxLhLArck4fBlNcjNQACYFvNTzwvNuHtXjhBxfXtSGsZzRlNjHTx0ryOCEqA3pYkpdYE6OaUEPUkNjHN87AcvYLpkomg44G7LFXO9T1+5jDHIEoXjcL+k0AiSlz1q+Jw0x3jegKZIiCkSsoyDgbs63Y7fPRH8ftl2IBHg7N4kOhMqJgpzO+oSpZgqmjiRN6BbDAlNKP/plu2PxvTuHw7AcRhYgLB68aZODM0IcZ51HTH879/ehm8+fRzHJ4uY5hwKITijSxjYzd0JTLawT78ZnMZnHz6IkukgFVGQcjsajkwU8NmHDzZdAwFga28c6zvjODJR8NdUDxwced3C5u4EtvbG59yP2u22xRQcyRTFtnilywTQULbYSc+8ng9CQ72MODCWx/HJoj+kgkOkPIPcHsMWE7W6EiK18s2nj+OC9W3+NBwPtTdoE05HQ0QVClWiWN8Zx6s3tuMne0b9hXQ+6XMpUH90HIBTMXIwuJj0pyMomY4wSNxlT7rvlUxH9DyqFH/3k70wbMFgXtMexf967Wa8elMHCCE4PCEU07x52IQ0rgnmdAuq61UnIzIOncjjqaNT2LE25Rs7ABjJlmHaDOkIQdG2ERietaRG2vMXbMYQJQraYgom8mZAMIO7PZ71qdGKwSL+vO+ZoiX+zt2UuMNnJRd6tc5WavFxVRLSrQss3DeK6luB17JECUEqKmOmZIFzYKoonDtFoljbFvFLPbIEt6RSvy3XXqI/HRVjS6kD283weC06w9NlfPqhgygYHhFPcCkIxHhVi3GokpgS5unPe8fVjFkuHFnuf6bV88AYx4lcGZ1xDYRz9KYiWNMea2qEposmNncn0JVU8YZzenFgLD/nbxyfLuGOn+7HDRet94d1aDIVXSRuqiGoz8A4QDmHIlFEFYoLawzmKze044L1bRg4UURWN5GOqNjaG69br5oeM+f45tPHUTKdqmPUZIKuhJjO12wNBMR98vaL1+OzDx9EpmAiGVGgSgSmI4x0TJXw9ovXt7w/Hp4/PoPJounPEZCoODe6xTA0XUZPSluW8ZYeVh3re+fOndi0aRMikQguvPBCPPbYY7N+/pFHHsGFF16ISCSCzZs349/+7d+WaU/rMV22RFrHTaFly1ZD6UHTFvUgRSI4PlnEwIli3We8GzSmSsgUTH+iVNVnAL8thkAY6L+85iz8zf+1A594y3n4w1evw492j2CqaDatTSsS8UVWCCo3jOSmWSUq5jQrMqmSNSUAehIK8rqDXNnyX/P+wlFJrekmQ96wUXbFKg6M5vGX39uNrz/xEgzLQUwR047a46qogTdxJqaLJvKGLWprRBBajk0WsevQJB7YM4rHD2Ywli2DM7GIlyxHtDAtz7Pmt1FxDjdVLX5YHBODZTM4jPn3h/i0WMBF+pCD8Yq85sETeRyfLEGVBLHFmkNZjVfsx6z72JNUYbps7YViod/kTKT1UxEZ00VhpHuSKta3x9Cd0KBKBGNZXfTPE7jXkvjn0kNClbClO4G4JgPgGJoqoWzagtUtieM0LAfTJQuHTuTd1iXHXXhdmqLbB8440B6TQQB39GqgdWoWSGR+50GSxH0xU7KwvjOOM3sTVc+4bjMwzqHbDJmCWWWE4mprMVfZEn32P9k9gvUdcZHm56K2S6kYqwouHGZNpuhLa+hPRxFVJGzpSTaMTCkhOLMvgVef0YEz+xJNjaK4f11NdEe0Xu4fyWMwU0BCk4XTz7iQtGWCRR9XZbyUKeC5wSyyJQvTJdN32iYLBjIFA+vaY7jxNWdgXXsMRd3CeMFAUbewti2Kd122Ed1JDcenShicKmFwsoSXJos4mhH/HZko4PBEAYfHCxgYL+DgiTwOjOXwxceOwrQZuhIqFIkKbXjHO17hyF60cZaU/CJjVUXU999/Pz74wQ9i586deM1rXoO7774b1157Lfbt24cNGzbUff7o0aN405vehPe+9734+te/jl/96le45ZZb0N3djd///d9f9v1vd9O8lsOhyvCnK9VCpkLCMa/bbu9tY8LCBevb8AcXrcdPdo8gUzCFPi8PMkQFIorwmM/uT+INO3r9KOwv/88RlEwHHXEVhl12RSkq9VHPwIMSEM/DdrfpeZqyRBDTJBRNy/89iQgSRlyVUbYcMbNXAhQqwXQcMFYhpXnG2rI5KAWoyGHDtDm+/KujsBnHqza2Y31HDIcninAdW/9Yg2AApgoGou1R0a/LOO7ddQxTBaOq7vWHr17nZyPimgRJImD2ycuHzgXGAFWmIITDtB2YjigRJKMyVCrB4QwSEeWDEzmjisHN3RPlXRuHA/c9cQyqRGA4HM4ce+9Ff7MZF89ITxUtX/3Mu6atnJv5fDb4HY8wBFTGec6URUkgoclwGFAwbACixmk4HJRxxFUJZYv50Z+3LYkQnLs2jURExtB0CWNZ3WegV2Uc3Puv5BL1HAYQUn8uOReRlMf0NVGdLvB+t7bcGWS9twLb8fp0HUwXTdx6/3NiLrxEYToWRmbK/jVRZYq4JuPfHjkiMg6l1vkpjAOHxouIqbrbX1+9DnltZpbDMJYzfP7JvpEcrvv8Lr/G7AnYeKcjWHcOPk1NysDVKM6uIf+h7z7f8vF5mCxZeMGVCF4o8kYDkikHjmRK+O/BGVy6pfOktt8qCF/MiQRLjEsuuQSvetWrcNddd/mvbd++Hddddx3uvPPOus//5V/+Jf7jP/4D+/fv91973/veh+effx5PPPFEw98wDAOGUbnpc7kc1q9fj2w2i1RqYfUI0xbDAkqGjZ/sGcNk0RAeY5Mz7wUHnIsH8tLNnWiLKu7DIB6BTN7AwEQBBd32a0oyFVGVR3wh7jYcziFTgjN7k0jHFIADed3GvpEsKBWqRbrlVA2u99CMjCOiwIqmtXcslKCKHct4ZZKQFyl6d1yrEZvft81bYy43UoHy4KctSWsp4BAhQoRohJ3veBXedF7/svzWqomoTdPEs88+i4985CNVr1999dXYtWtXw+888cQTuPrqq6teu+aaa/DlL38ZlmVBUZS679x55534+Mc/vng7DlGT/BdXd7kVBA2IYTM8cnCipe+ZgRCztrZoORzPB2bb+nCqPcZa29XIlnFUE8qCRpFxbz/qv7nQHt75MpbrGOlNthkiRIjTG17Q45ExRSYvMKySVHfTELezwpiFrONts32ZGN/AKjLUmUwGjuOgt7e36vXe3l6MjY01/M7Y2FjDz9u2jUwmg/7+em/o9ttvx2233eb/24uoTwbzJTKEeHmhYdbCTeFWUonV75EG318M58Pb1lwZB8nNcCwk3d3sdzd2xjCW02G7s7Y9Sc4g7yGYvfF+mxKCuCZY0brlIBVVcOnmThACZEs2njySqctgSVS02hBCYNpCMc9mvDJiFRUSn0wJIgqFKlMUTQcURPAbGsBbxBkXbYVeFslyOIqGXeVAy1Tst0REe6QqEVyzow8bO+P+NX5pqoSfvTAG02aIKhIkl4HttSP9jwv6sakrgbGsjkcOTrREKAuiLSIjEVGqzieIyAKatoP/deVWbOyK+sbM+xx1d5Bz4B//8xCGpktojyn1hLeShQ0dMfzltWdBIoIwQ1EhdhIC7B3O4m534llCq5DBCoaFmCLh/a/figvWtdUZWW8blFRvL/jefME4x19+dw+eOz7td8F4vwm4LaYEuHRzJy7Z1LGg31gIVo2h9lB7AbwJKfP5fKPXPWiaBk3TTnIvqyFRgj+4cB0m8gaePDLpD2koGLZPAmuUXk5HZfz29l7f0FMi6tqPH5qA7Gr31kLI3jG8/uxedCXVOkUj4UWKX3xg9xhGsmVXhAI+E13Umur3R5FED7RoUeCwHMDhwvtMRxTkDRvJiFzxVt3jmi5ZcBiDJkuIqhJkVwt6sjB33zYgavtxTYJhM0wVTaiKhM54ZVHQbQeTedMdWCGUvKZKYtCFRIDOpIaIywY3bY4TOR3cPb+5sj0vTehG6IzJyOm2z96XAPS2RRBTJHCI49zUFcefXLEZed1CW1TFtt64kDl0wThvyJz1Xn/62CS+++wQupMapJp7t2Q5GM/pVRkVQPRlB3uy54JEgN6khvG8AZu7ZESZ+OfZcZivIa0qghdtWEJrPfjbje7nuX43GZGRiMiI6RJ6EjEcny6hbLnKZYH9VyQhocvhtlgR8UwnIzLKFkNfTMH/+z/OwSWbO30i3s1ffxYHxvJIRxS3DEShKaIWPprVsakzjuteuRY/PzCOQ+MF5HXLVdYDkpqM/rYYzulP4ucHJtCX0qApEo5lig2JoF1xDSXLgeWInuaY+7x43QqyRLEuHcHxbBmGKTgJsgTs6EnhHZdswKs2iMXfG17yF9/dDQBY0xapM4KZgoknD09i73Aex6eKvu77fBy2RFRBTKlXFtNkiskSQ0dCwdl9zUt+B8cKyOR1tMfUhn3MbTGC8ZyOos5wZl+s4TauOqsHqajit3mVLNHmtbUnOXcf9SJj4EQRhyfyPrHOdsXWCVz1RS54Hm88t3/ZGN/AKjLUXV1dkCSpLnoeHx+vi5o99PX1Nfy8LMvo7FweEgAgyCCf+oML8JM9o3h+aAadcRWUCK/8RFZ3Fw+3nswE+asjrjbsH3zm2BSeOTblb6MWjHNMlkxcsa0Trz5jdo8vpsr45/865HvI4j6sHvLhE8SoIOIUdBvpqIKS6fjEMADQEhQ2ozBtVtci0ZVQ8ebz1+CZl6ZxfLIo5AUJQX9aw0h2bhJMVKWIqTIiitCp1mSCouEIpihEm5I3ArQvHQUFQVa3RfTFgHzZRqpd6JiXTMtf5Eumc9JGGgAmS3bVvx0A41kd/W0RFAyGuCbjf16+Ca/a2F7VF0wgtKW99NtFm1T/OnjvgwA9qQjaYgoe2DMKcKH7DvE1FEwbozPlhn3KFuPzausghCCmKWhjwgj4aUG4Ebv7OU/ruDupIpPndcNcWjXUnkO3vj2KGd3G6IyOzrgGRZbQk4pieLrsjiMU4BBkOkUSz0fBsGBYDAwcusVwTn8Kbzy3D4os4Vim5Pfjf+D12/xZzd7M9+myiYm8AcaB0ZyB+554CZu7E/jzq8/CurYopksWRrMlPLRvHCeyZTy0t4S8YaNoUnQmVPSnxf4xzkEJ8cloBcNGOqbgxsu34LGBSRweL6BkCm3tqCJhqmTi+bzhS6pGNQnXvXI9Pva759Qt/HuGshiZKaMrofljG4OIKBQDE0UkNQNdSTHpKqJIGMvqc55/CsFj8aRlvfMr/uQoloUSV8kQkTulxM/s8ABXJG9Y/jVpdOFViSDPeVNCrIeTbfNaLDw7OI1sWawdtfPUbS6OR1MkrO9o7HQsFVaNoVZVFRdeeCEefvhhXH/99f7rDz/8MN7ylrc0/M5ll12GH/3oR1WvPfTQQ7jooosa1qeXGkHWtyYTxBQJvekIJgsGTLuidLSxM4b3vnZzQ0/SU8zxtlEL0xHeaDoyd/2kPx1BTJHhcNEq4bNUA5/x/m4zYQhtxpEpmpDcaAZEiADkdBsSBboTKmZKFvKu+MHm7oTvFb/1onVVD6LDGD7w77+ZW1vcjTxNhyOmUPzRJRvwvf8exuhMGcGghrppRi9NqVsMEhGTmnK6jbxuQzcdn6FaG4EuJmwOjGR1nNOfwu3Xbj/pubwXb+rAtt6kkGxUJYCIGbmjM3qdkQ6ul0LJTQzIaAWaLFp9MjDdtpQKYTCqUDhcsIE5EwMZupKi19Vxt08gpi0xLgRPGrMVBLzXT+QNQUCUqD/kwdNrHsuWq4aIKBJBfzqKhCajK6FipmyhZNi44dXrsWdoBjt/MeDL8galZIM68hOmg4IhWrX6UhG0RRWYDsOBsTyGpku44/rz0JvS8E//JfqrNVmIzHAIzsjIjI6IQtGZ0FAwbJQt21/QTUcMH3lsYBI3XbkZ6aiKxwcm8LUnX8LIjF51jQgVhvC+J15Cfzria/l7qB18USvTmSvb4BxoiymIue1ZXQkNmkxxfLo0q/44h4iap4om1rfH/G0XDBvjOR1lN1PyhUcP4+cvjjeV5J0pWa4cMKDJlcjccyrKloOIRHFWbwobOmKBtsxqSVDv333pqE+Y9doJOSplC0+Lu5Zt7jPRUe1INHqvGRjneOyQ4ANJBKCUQqLud93SCSFATKbLpkjmYdUYagC47bbb8M53vhMXXXQRLrvsMnzhC1/A4OAg3ve+9wEQ9eXh4WHcd999AATD+1//9V9x22234b3vfS+eeOIJfPnLX8a3vvWtU7L/Z/clm6jocP//ZQrElOaXpZkSDwdHtmwhp9voS0WxqXNujy8dURFTKSKKAoDA4WJcZW27hgQRJQaNIiFuHzUh6EpqiCrUFRxQcdvVZ4noJargrN6kb0AJgFdsaPNT8PtHc5DclrDZTKbs9rMWDRt9KQ0P7zshopngZ1zvdzxnYG17FL1uROZwBs4ES97b74rASPXxAPVEtGBGwbN1Xuq+EYJGknPRKz8XWhnQ4o3j/Oj39+D4dAmmLVq8Gs4yDuyHaTN0xJWWDLXNOI5NFhFVZUhEOF0RRa7oSyuiRjs0XYLNOEazevUgBwDtcQXtURVF08EkM+DMMS9dogS6xaDIFKqMqiEPCU3G5q44jmRKQh4TwNq2KGKqDM7F/PRc2UZPUsWPnxtC3nAQU2UkIzIoQZ2U7KWbO7FnOIuPfn8PhqfLWNseAXVHdwXnKO/85WEAHAXDRkKTMTKjw+Gs6trqFsMUM9AeF/KSBByqTLGlKw6LcewfzeNjP3gB77hkA/796eMYDRhp7xo5Aef3n34+gHdfegZUtWLsOmIqZCqEfCRK/GtAiDhnhi1KA4pUnbpORhRs6opjIi96rSdyetWzG5EJOhMR5HUbRcPG8ekSupMRWA4TzwwToi9rXKGYZpK8jIm+6I64iqHpMta0aTBt+PeLphBkyza29ydx/rr0sqaKZ4NnyHnw3xAZjGxJKCZaDgOFkDz28t4OZzBtjt626LIpknlYVYb6bW97GyYnJ/GJT3wCo6OjOPfcc/HAAw9g48aNAIDR0VEMDg76n9+0aRMeeOAB3Hrrrfj85z+PNWvW4J//+Z9PSQ81IBbboIqOIhFMu+o3gHhoO+Iajk4Wm0rnNVLiKRoWpoqWf+O9NFnEW7/wBN5x8Qbc8Op6IpwY2SaGEWzsimNgvIjupApCKDI1kn8Eon7NWXUPLuMiwupORpDQxG3UmdAwmi1jbVuspYky+8fyiKkySpYNx+F+NB9c+CmEcEm+4ECRCCYKBqZLosdWk4QYheWItKMsiVa0ibyOMzrjlYiMMaGK5qb5HMbrGegNjLf7stvmJir4MhUzwGfVm4ZHyCLIle2mUqZA4wEtzYaKXL61C++4ZAM+8/BBMTJylnPLA38269dvhLLFUDKFtKxuM7TFKAipGIK4KkGVRP3OtJlP8FGpyFBMFS1MFy2fUTu7kRZ/ypT40fpU0UR/OlIhClGK3pSGwakSqDt1Kle2MJ43fON91LRdbW6gYDhudEfRldBQMJyq80+JeOa6k5pvpD14Q2JeHMuDg6MtqmAsp7tTsygYFcNovGMSw1RE+lyhBGvaopAkCkmCa/R1fP6Xh2G73/HOCRBoUXT/LOg2/sfnf4W/efM5/nXPlk2UbYZc3vCfWU0WzxxjHA7niCkSImp9gUOTJKgyxd9ddy7++eeHcGi8gKQm+9wWmVK0xWQcnxIDbYqGjUxBTLmLqRJ6UpXnupEkb/C+LZoO8rqF7KhVJR5EidDJXk4Fr1ZASK3IkfhH3rBhM6EBMTqju1OyKu2ezBVKuvbcvmU/nlVlqAHglltuwS233NLwva9+9at1r1111VX47//+7yXeq9bxyg3tuO0NZ+KbTw1i91AWFhNpFk2W0JFQfQJSpmDh3585jovP6ITkks+8VPPrzupBXJPx1V3HsHc4W9WUL7ufyes2vvjYEbTFFPzpaze70pP1JLpbf+dMfPT7ezBVtBBVaEN94qDiGMTmsSYdRVtMqdpe7YCNudARUyFLALUIbFSzcoPPgeVwnN2XRLZs4vhUSRynRN3Fi/uMXi8SMGwG3WKuUaGwGRfZB0IwkRP1wWD9CWhuUCQIR8WbAx4czNAI3na8T0VVyZ8OVuu8BCd4tcdUn3Q0WwTz6KEM4qqEtemoUGlqwQgzDsQUilIrc6jd9F53UgPjwFjO8Ou6hsMw46ZjQSqjLDnnVYQvL91NeSVTodQQzgCPjyFS2RIVBlSVad1vFgwH3UkNPUkNIzNl3/HQZAlRhfrnwGGATDkICMqWSFF3JdWq89/KHGXT1cFlHFVTsyQAkClst0zkyaRqMsWatqhv2ADxnEUVCSMzZVcdLXB+mtxsQ9Ml/7oDwMd+8ILQHXezToQQlC2R0VAlCZQQtMWqpUU9eGMms2Ub4zkDbVHVVUI0/VKGJktIRxUwxvBHr96Ar+46irgmIx2tfq5rp9zldavqvlVkioIueCLVrZpi0MjekexJl36WA97oTlWi/phMw65MzVJlCTFVwhVbu5d931adoV7NiGsyNFnCmvOj2NARx81ffxaKRARRSqUuM1s8IJ0JguHpMmbKVsPo9I3n9uP1Z/bgVXf8JwAxO1YilcEOEhVpmn979Aj+9IrNTQ1MsH63byRXlTYFKhFlUESEQ0SntUbfWxzaogr2DGUbpnKDad7BySKKpiPGYEou65yLqFhyH4xNXXH8nbtw3fz1ZxFTZT9qAsR3ZIn6NX4x1pCgaNqYKXMxzIAQtEdVDE6XwAB3pjCFTdisvd0yJVjbHkGmYMJw660Oa23ohSc4E1Uk5A27znmpHXjvnctgCrY2EveGiXTENfe4RLTcSqXd4dwf+zjb5ykliKsS8mUb//fvbMND+07488FlIuQ9J11FNUJExqPZOGmXMAugwgegpDK0grn7FFclf/zluy7biF2HJ+tmkt981RZcfEYH3nr3E7CcAroTGqKqhIMnClW/KaZpisyHwzmyJQtRVfLPfytzlFVJqMPpluMbNQ8SEbV0h3EkNRkzZQupiOyXcKoNXOVZ8TDbrdMeU1AwHHz+FwMYzxsYz4uxku0xwQMwXOkyh3PIKrC9K+kqh1X/bnDMZFtcQcGwUTJs10ElbiZDzJk2LAcxTXadUTGpq1FHjOeEZ4oGvvL40arxmKNZve7zEnXvDYfjMw8fxPb+FK7YtvwGbj6oHt2pId4Vg24y2IxBIgRZ3cL2/tSyp72B0FAvKxSJQpFcYzWag+VwpKIKoqpU93A0ik5ra5kHT+RRNmyhx02rIwRv3GS+bOFHu0dx/avWNt0vr373w+dG8Lc/3gvGOWbKgsnsV9FrFpjBqRI2dsaQ0BT3fbE49Kc1fOrBAzgyUaxL5QLw02WmzZDTbTicuS02IqVMKUCYiKIlzvGRa8/GBevb8MjBCViOaMPxFkC/fkyEF+wR4kTrGMP2/hSu2dGHnb8YQN6w62YKy25Ov1YchgDQFIq2qIrJggXDcvzouxXRFuJeq5gqgRDhGNSSTxoNvPe/XxPBeI5abTQYVSVoiiDNzQXD5u7AEmFkvZK1JlM4jPn/thlHVhfX/suPH8UnrzvXJURl8ODeUbwwnPMjZtZCgF4LxgHuVAZfGBZD2XJAiNDrvmJrN266ckvDmv2eoSzGczp6UxFEFAmTRUNEvzXg7nEI/W6GqCr557+VOcpn9yUBcLwwnBOdA+CC1+AabcfV6y9ZgpiYKYjMhiqJNH3S7UsOqvXN2ZdOCdpjKo5Pl/Crw5P+6yVTkLq6Exr6UhHYjAmtbMZx5bZu/J/fDGFopoyuhApNktysh4WEJuHmq7bg8EQBOb3SlcBcJ0tx50xbNoNuOehPR+d0YBRKMFO06sZjGrZTd2wOAxgRBtu0GT790EFcvqVrRaXAaxHkgfhZHZkCDtxzKp+yNH5oqJcZuwYy2PnLw3hhJIucYaFg2IioFD2BWi9QeTC8BaZRLVORRF2vAfnbZTeKlPCzg1N4yyvWzHqDUUrQnVTBAGTLlQe72drCOHB8qoS17TEoEsVMyYJMxai+0axel8q99dvPARCLXHtMRUThmClbbqpVtInYjFcNZ4+pEtJiCK8fCXnDAsqWmL8cFDqQKBBVZGzojOGO68/DeWuFgXtw7xieP56ti47cMfPQZALLDQvb3AjG4RwjM7rffgMq5ndP1bRiNQKHS7JLaD6ZptYLbyUFW+uo1UaDBAQdcbWKTTzrfnExxjDYfmc7rOkIysGpEv78O8/jT6/YhPufGXQnWbUSv8+xH6h2eIamy4goFOeva/ONcqMsUvCccXBk8s1LLJ6x5hDMbu/8N1yM/bS+MHC3vE44lbd/bzfyhuWK91X2l6Ciae294zCOMnPw0mQJPSkNlIhngXMgU7Aw19qejsg46DqwtXAYx1hOR18qgu6khpxuIZPT8e/PDMJhgll93CyLWcmq5GcgAOBz/3mw4bkxHQbFHWTNObC5Oz6nA7O9P4n2mFJ133qOQ0N+BxfZFkKAwcliw/LPSoOXYdz5ywEcGMv7a+3ZfUnc8rqtpyyFv+qmZ61m7BrI4NZvP4enjk6iULb8NG/RcHB8quQOHqg8GFt6EtixJuXXMveP5hDXZPQkNcQ1GVNFsVDVEpscxmE6DJYr8v/j3aN49z1PY9dAZtZ9+9gPXgBjHA0yXz5UifqTihwGjMyUUTRsrGsXUY5hOehNitQspWI+dG9S9Sfe9KbEe74+ueSl6ik2dMSwrj2KjR1xbOqKgVLiG6oda1LY3B13pwbJ7ghC5g6jZz7JJxGRcbsbhVOX+HXzVVsQ18RvOpy77R5ChUoQXjQxEIQSdMQ1RDVvIhn3U/yEADG19Za+VFSk6L3IptZJChrdRqh11LxzsKUnIdLd7vlTJTqnEfDAuWjfiaiSn40IGmmX3lD5OwEmCwY+/wuRok9H5QUrPs0Gw2YoGg6u3DZ7xBU8Z1NFs+m58yAIfcAfXryharveYry9P4mSYWO8YKBkCIfK4wVcvrULf3zpxoZ9vB7hkaN+AeUATuQMjGaN6vYojgaVZLF/HW7Ku5GRBirfmygYKOiWz8yOazLWtUexoUNMt4rIFLf81lbce+PFuHRzJ+786f5ZiYSeQEpUlZDTbdx81RYkNAljOQNlywFzFdDGcoZ/H3cmtKr7VnL7q2cDd2v9rXJXVgYqQj+k6sk4NQgN9TKBMY47f7pfsEQZh+T2jHqXX7S7lFEy7aoHA0BVLTNoADd0REEgDKbDBKFMMJpZVdqtK676BKVGxjpYL+2I16dia0EpgUwF4SgiUyQjMoamyhicKqFgOHgp4HQAIu3KXdKRYbkGmrrzbyGY2ILBS5CMiFKA6XDfUDHG8c2nBzE0XUZOF4xfb0CH0OXlfj3UsBzc/eiRquO8fGsXPvXW85GKKuL8uOMCI4qEte1RIX3os2oJdJPBsB2/lmoz7s7sbT2adByOde1RfPK6cxt64Y2MrjgEjpJhYyKnoycVwfa+ZNV595yOoZmy6L93WEsPsXdFVZnijI4Y4ppUp2znpbS9L4hpaqI9KKpIdW1AiwECQXSLqTIePZRxOQYV2DbD9/97GP/yX4fwXwdOuDO8DUwWWpsW1RZTsK4tij1D2aptX761C/feeDHufudF+PQfXIC733kR7r3xYv9aecS9VERGfyqCiCLY0rV+hOr27DfyL2QC9z0CTqqzOQRAW1TG9r4UTIdXCbvUIsgyH54RRjqqCCIYpQRRVRhsh4vsEQDsGc7ixbHCnOYlFVUQd0sDrTgwze7buaBbol1zpcMLig6M5fx7py2m4MBY8/VzORCmvpcJe4azOHhCPDhChIL4qgcei1S3GLJlQVjw2nP2DGWb1jIpFQpNk0UTpgPIXNRSg49PTzKCqCoLxaIGBCWgUi/12lG8Omajx9B251vGVAlRmSJTcDCW1ZHQZL+Vq2wxt09VMGG9RYhzuH+XEFGon8L2VNm894KptmzZxFs+/zj2jeZFGhrEN5isQTSoWwzPH8/Wsaav2NaNf/2jV+LD392NkmEjFVWQjMgwHY4TOROdcVVEQ3kTqiRIV0QStVyJENFn2qoWp3ueTmTLuPvRI6CE1BnrRilYy2EYzwmmKQAcnyrixnufqWvVSkVkjM7o/pxvL7Kbbe9EplIw5E/kTXQlNGzqiuEXLzZeeDgXRCA/wiZCyESWZm9Nmw8kStCb1NARV6HbDAMn8vjhcyPoSKjoiKl44vAEdj5yBLmyVXetW92DbMnCh77zvOhxrml7a5ZiB8Tzun80B02WEFNlqDJxW8Lqs1cypaAyhWGzquhScjsTVBmwHEFO5OCwbJG1yuk2yhMFWHNkBoIw3VRsT4CACNTzGn5zfKal7eoWxzlrEn5pwOOrNOvrr71v1Tm6IDyshnkHjHHs/OUAZkom0lHVL5VFlOYEz+VCaKiXCc8NigdHppWUCiCMAHVbPhwG/P6r1uEv33i2fyPMVcvsS0Wguwt72ahM0vUIKN1JoVvejKAU/I1KOwoFr+kZ9SCkOkX99URORDXJiOyq9ohjU6hIq03kdcTVuE90IwSBvwvjNzxdhu3qIFO3/cSrFV65rQt/9YMXMDJTBjh3FwW3ll2zcKtuX5rhCJbmVBF1D9UV27rxmT+4oKJQVTChUFF/euO5fcjrNh7cO4ah6ZJPlgr2iue41ZKRIO7BxjW5aasVUM+4nykJ7fOILKE7qdWJTQDw22I2dERd585BTrdQbDQ3NwAh8yjq09v7k7hyWxe+8qtjcxxJJX3MOeZdE58NEgHWd0SRdMmIls2QKZr45E/2gRKRYQmSoGr3qVU4HCiaNjRFnfVaBLFrIIO/e2A/poqmKw+q+zPUJUrAglPqHA5CXIemZse4y3gkrnNp2CL7QSlBZ1xFQbdRdglprS77EhWtkQmtfukO8hqOjOdbOk+aTOpKM7M5MED1fXtgNN+S56QpkuCkrGB88+lBPH10GoxzFIxyVd96QpObrp/LgdBQLxN4sPhXAwJRS2Wco78tWvXQtNJOko4o2Pn2V+Gne8fw9SdfQjqmoKNBBN6szzmogOQwDkKF0VRkWlc3IwA6EyokQqC7ghPjOcMn1AhGLPUZt7qrze2luTWlsk8JTcaatgiGZ8qghCCvCwb79v4kbrpyM+5+9AiyborN65sGhKNg1ER1nvdLIVLVpu1g4ES+7qGqjRiOT5XwsxdGsfMXA+6xCia+IlGUDBvr2qOgrnOhUKF57MwRUcp+DY+gL6XN6olfvrUr0HbE/LYj79r1pgiGZ3R88if7oMq0rp0rrsloj4vU3GwBFAHwe69ciz++9Axs70vixnufQdmc3bh7iKkSypaDtKtCNVkwZx0DOBsIhLFb114x0gXDxkhWpHRjqoSkJuPAieopUM2U41qBYTNM5E2saYvUCaDUwkt9zpRcAhjnfh2fc4Dy+myT7bjObe2xevsM7usTUDcFrkoU3UkVZdPBeKG12m1EoWiLKi57v8FxuryGwckivv+bkTm3Rwhw6xvOrHNaWlHKCyq93Xr/cziaKfrnpfY8aDJFUpOWXXZzPtg1kMG//PwQLIdBkQkoCDiqs4MxRZqXTsRiIjTUy4RXrm+DTCkch4FK9X2PjiNSaK9c31b1vVbaSbb3J3H++jZIEsWPnh9BXG1M+mlEUAIqCkhZl+BmOhyUiP3xhmsAQqYTEGzz0VzZXzSpVJnnajmCyOZ91utn7oiL3zyRM+vELNa4OsfrO2L+wuCl42OqhLxuwRt64LVmefAWB8udge29Z9gMuQb9y0AlYtg1kMGXHjvi6zmXLQeGzTBZEpGzTAmOT+voSWnQXKYxJSKr0MxeeK04DhOpfEKkOT3x/WP5qrYjDiGPWTAsZMs2LNvBfk+NTZZQNJ3qDgGL+/srzpfdcP8ePZTBmy9Ygx/tHsW+kZw7xW32tiEK4H+c348nj0z5KfqoQhdsqDmE4edc1OI5F1KktsMRUynSMQUzJatunzxHLNjP3wq88+JwjkzBQG8q0vRaBLkaa9sjODzh1LW+2aySYfC/xwHGG5wPzuHA1Ub3vs8BONx1TuHL6bZySK/b1oWixWZdC/rTGnb+8jCKxtzdCf2pCN5xycaq1+ajlEcpwQXr2/CJt+zAn973axiW0EPg3L2nuMgAaLKErb31nQ8rBd51N9xpbZ6eBQGqsoO9qUjD9XM5EJLJlgnnrU3jrL6EMCouW1kIzHNf8P+svoTfUuTBqwnNxcaklMxK9Khlknvw2N7cFRnxwLho4bCZEKVQKPENpeMwUErdejtxJz4R17BTv0+Xca+fOYnP3fAKfO6GVzQkqtz5e+fjjy/diKvO7MZ5riawl473HnrT5v7Ag2BrDw/8GTxiDjG0wlMyq0VwUU5oMibyJnSbQaLEr7s5jEO3xJCCE3kdZdPBWb0Jf5SnRNx+VOqxQ4ViGkCq0vyaRGHN4okHyxsFw8axTAlHJ4v+9Q4ys03bwfB0uYqsZzPmk/VMh4FSMeVHlQQPIOKSnaZLJm762rP46x++gKmSiemiUKkSveX1+yVTgva4indccoZPMpoumlXtewtBTrfx0lQZhzNFHJksQXdLLIwDRcOZvbY634iaeORH4teQm12LYG97yWQNVfrg7mft6eKoEM1k9/dEZoc1dCy84yVu5NbCYWBoRsdNV25uuhbEXSnRomH7UftsyJUtPHmk0rPdrLtkNiIqIEpKf/6GM0VftuM9++4xgiCq0hUnIxrE3pEcBk7kkYhIkCWPM+QOmSGVe2eyYNatn8uF0FAvEygluP3a7a7GMPFFCxwmWoS6kxpuv3Z7w5u5FTam9xutGnWg2litb49hfUccUaX6lvDUvmy3bWtNWxTXv3IdEgpFVJEEeS2wEklU9EQTiPGMt1+7Hfe8+9V+y8tsTNsgOmIqGGfIFI06A9xsYSOBCAUQ6fufvTBWxyQGqgl0mYLh6jkTtyYpFk8xKUqcv56khmvO7UNbTPMNs/c+556RJm7qXaRCLccRghCOM6sn7pU3Zsqi9Ua3HL99LZhOJBCKZ4wLjWlvMIVXnuBciEtQIkopkns8jpu+1S2Gojs5ypMKBUSpQKEEmkxdx0Ncx4Qm4Zw1Qonp8q1duOnKzVXR4WKCEpHJOT5Val5v5/O305LrRLpZbJSt5tfCc5gUSjCRF6Mim2SZoSkUGzuiohsAIkvQFlUQcRnsPSltzn0VTvvsn6JE8C8kSjCW05GOqk3XgvdeuQWTBdNngwefhUYoWQ7u/Ol+MVyjRikv2F3Sl6popjd6lgBgx5o0OuKqz4ynBJUJeyscjw9kkCmaOJE1YNniWTFsDtthQmuBc7/zIxQ8eRng8q1d+NwNr1hQM/1cbMzg54Ij/WplGIO/UauOldBkbOlJYKpoIpOv9KlSl/nYFlNQNBz8n98MQbc4upMaRrM6LCbmaRMANq/U4/IlC5956EX84Llh/7fnIqp42N6XhOMyjxU3OvGMVaOlwj8L7mJOCNCb0nBkonGas55AJ9JdDudVJDrJZaS/NFnGwRMvIa5J6ElGkIzIGHaF+wkRRDfb4XAgDLcJB8MzunBiCHBGZ7yq1SoI0SOewFNHJ8GYqMc7dn0t1FP1ogQomTYOTxSF4ITDK4xvLtSnHHc74PVqatSdBGa7OvOew6HKYpG1mfhMOqr4CxNjHH//swNNCV4nC5EqFftZaJK2bXbdRSTX2IAEZy0TIrIs561LN4yKPIepVsWO8eoJYR4pT6YUCU3G+v4YPvjb29CZ0JAtm7j70SM4MJqfc3xrM1Rdd/cZiCqCnzJVMnHVmd0N14LHBjKwHI62mILpkoSy2bgE4v0GAfDiWAF7hrOghPiOq26xqolpsxFRgYrD7zCOs/oSMCxeNUHrRM6s4wW0UgdfDuwayOC+J465AzhE5pC459xyAykvO/GB3952ygRPQkO9zAga3EzRwEzRQntMQTKiuBOAmt+srRq5Vo16I0Y5gYg2posWiCMWt/aYgrgmQ5EktMUEualsOeiWVFe8XodhMzAmBFwAYdx70xFIlLTMtg1i/1geEhGRBIdYjL3hG43A/f9zjXQygraoivGC0TDN6S3KQT1nQfoJTDqCiMoZrygw2Q6HplA34qD+7F6wSjqTut/3FZs4cDRTxPV3/arhbGpKCd54bh+ecNOQjZSe/MiaV2rKZcuBTBu3ZTE3uq6FIHNRECImiDlcRI02g98mSF0mfHBf9wxnBcN3hcDnZrpMbEpEeYSjItfpfYZxkcamlCAdbS4D6ZWOgip2npa857wRN0q0GTBRMNERV/AX15xVdU0v3dSJ/+/BA/jK40erxinOhlqugHe9vS6LdEwBOGatj3r3tOUIJ3pwymla0FdcOVnbYfjN8Rls6oqjaDjIli2YDgsM7hCs59mIVEGHnxIKISZYIb7WGvn51MGXEp6DYTkMUUUSvAsKULcg4Z1/cCCpSDijhdHBS4XQUJ8CUEqQ1y185fGjS3aztmLUGzHKC4aNsaxrfCCe80zRwpTLglUkCTFVEKsm8gbWd8QQ74yjbDkYnimDW9zvs4657OWF9CBOlURrzNr2qMsydvwJYrIkPPyCLoYKCK0xsU1VouhLa0hoyqxpTm9R3jOUrRDUOPw0trcoM/c1hzF/MteUq44W18TQkJmyhZJhI6ZKGMvp4Kj0Ggsyk9jOgbE8bv/ebtz5e+fXXeP1HTEkVNFzHiRq1TJpvQjYg/dRRSJuiq7+XAaNgJcO9XTORaZCtA8lIgrWtUfxRxdvwNtr1Ly+999Dc6Zplxve9REkJuLPDOe8wh8QDlZj56MWXunotm8/h7whPCKPiyGIW6JM5WWMNnfH64y0Z4T2DGfnFVELh1B8Ifg1AqAzrsK0uS9F28zQ3XTl5qqhEm1RBZPFesOqSKRKSpZwIQdcMG3A7bDwngmP9dyVVOcsGbQihzvfiXFLiaCDkYxwDE+XYdn1krre8/uxH7ywrPtXtQ/L/oshVszNWssoL5qCqNRIJckzWDZzxBAFAGU4GJwqi3och98PLVHhhVd0uGdPnTVCcOTcGYEpNjKliKhiEAUFQU93AsemikhHRMTvTSELMuIbpTm9Rfn27+1G0bRhO8ytT1cgtIrdVwIh+4mcAUoNaG6/czqioGjY/3979x7fRnXmj/8zM5JGlizJdmzHduwkkJBrE+iF3H4poduSsFs2NHxLodBAaQssNGXJcunClm/pjXAvUH4EtvTLrXzLdrsJC20Jodsk0AYnBAgJqUmIE5I4seM4tiXbkkajmfP948yMJVu2ZVmWRvbzfr3SEl/io4vnmXPOc54H4ZiGKRM8ONGpQGGasWdtLp/yxMHgAP2pyzwueGUJHhcvvHK8M4KYqve7aIsi7wUN9AZgp9ibuAZoRgep3gt+YsDgrUH5zzX3u0s9fDXnrovmpqwJr+sMbyUkEqWbpZzu1w3FbKcpAjB3r52SYB2Vi2t8dcDM8C6WHdb+PABU+uWUNx8DKS924WRI4Rnaug4B/GhUVaAIIgS0dSs4o6IYv7t+MRwJm9iJv9cep4ROpH9umOeq9M/AFwS+NVPi4dsQ9YdOD3jt+MHLH+LKhZNxrD2MlpCCIpcE9CT/e2YDH4beo5Tz6wJ4aPOB3pUIobeAJs961nGqS8HCM8oG3TIYqqFHSZETD27eP6yOcaMp8QbD7eSd8o62R5JWIQQAE4plVBQPfsxytFEyWY6NNGkjm5KTz6JoCUah6fqAb0LW579dDhExTUNHj4LTPTHoDFZZTvP4kJnwpMZ1hFUNbT39Sz/qOsPepiC2HThllXpMzGAH4/WIzfKiYLAy2G9dMQMlRU70xHh0YkaTglTJc30tmV6OdZfM592ShNQVtwT0T4gx+4NHVc1qRWoukTPGZ3FOSUxqO2omMyX2p05kPt7OSBxFTgnVAX6ePmlEAqxZkCvhXLmQMECHMQMc6N1jnnUHeo88xXWGuZMCAzZu2XciZFVBwyD/dl+lHiecaVauGuyrJFGE0yFYS/z8uJVxrlmA1cJVEgXcddEc7Pq3L+HZaxbgwa+djf/zzXPx6pqlvG73EBdXM9C2hBRUl7itxChB4HuWsTjvLFbqdeH2FTOTgnTf32uPy2Htj6fD3G4xG89Y/y4DakvduGfVPCw6c0K/a4dg5FB4XSI6Iyq2HWjDT7/yKVQHZJzqSl1mVU/Iw5gxsRiiIODQqW5U+tyQRN6TXjdq4pv3pzrjrXUH2zIY6rQJgLQ7xuVC33r7ksATA80JgtlhzCc78zK+RBSoc2w47Q1zwUw+qy31IBbX+h9U7kNI+P9Kn4xi2YEJxW7847xq+N0OVPllK0h3K3F8croHR9p70NQZQVdExaN/+jjpmMf2g224+pmduP6FXbj1tx/g+hd24epndqL+0Ok+Gexx9ChxnO5W0NQZsYLw0rMq0sqIH+zx//d3l+JHK+dido0vKWCYy+x9t/l4Vqtg7JvraO2Koq6sCEVOMWUPY6B3Kb3IKaU8HtQ3Y18SBevsee/PFSA7JEhGRq95zUw8wmsun4rozVgWAauRCgM/16vpmrECwmc6g93QtIdjvOJcmkHXFI7Fcdm5dVbi0mD6fl5I/GPceTDwG5Ra47nmx596kxd1nWHj+8ex85N2zKsNJB33G0rfQDvBK6OuzAOPiz/fceMc9qyq1O+rvr/Xbhc/FTGciZco8ix1hyRAEvgNiVeWUOKRrZyTxJ9hHuU70t6D451RdEdVvPNJO/78UStCERVFThETvK6ki7yq8SOToiig0ifj+xfOwvvHOtGjaJAdImpK3FbTHDNgu50ST5orS71Hm+5pk86IOuQS+WDHGLOt7w1G3Dgma+Y86Izv0bud6R2zHE209J1jmbQ3HG1LppfjnzUda1/ajUCREzFNx8lgNOVRKPPOXxCAjrCKcExDR0/MSKrScbQjgkkl/KbjeEcEGmO8zrTO4HJIaOoIpyyJOdAWwD2r5mHdaw04cLK3JrJD5BegD5qC8LmdWHTmhLSS5wYiigK+sWgK5k0K4Kpf7UCXErcqaEEw00p6aTo/c564tPy/PlOLzX87ib3HgwAYGOs9m2we7yhyigP2pzZfh8SM/Zim8wu2JKLU40Kx7IDbKeKT02FEVY337gas2Q9Ybyc1h0MwSqD2JuE5jcx0BiCm8cc31L4tYB6VY8Ne5YnGGaKqjjKvE5GYDkXToadIlAN6E+KMrXPra8yX0MzqLit28YpmjLfHFIyAJoBBYwIOnerJaPso8bheYtbzlDIPlDhDTywOVdNx24qZOLtPUSKg/++1AH7k8niHPmCXL8H4HysvwthqEQS+8lLh48mY5smFvuftj3dEoDOerSyIvORtTNPxQv0RFDklTC7zQBAE+It4I5NILA6d8dd9wdQynD+zwspQ71JU9MTicDtFlPtkOATReg4gMIQVbdBEtnROm+xtCqa1RJ6rgiJ965bzo6m8sJLOemv8mxOqXI8vEQXqHEt3PyfXb4ZyrwyPS4LLIfJlW2P2ZF7YTb2ZtEhqoedyiPDKDjQHeRcth8h/0UUBiGt8NjjRL8MrSzjeGcXP/tgAh5FUVx0oGnC/6vrzzkyaHegAOntiONzWgwde/whPv+XEnJpAVpLw2sMxCAKvY94VVXmxCvTuBwsCrF9iZlxQ3U5eJGHyBC/f8964Fz0K3/N2JNQmH6o/tanvqYBH//QxmjrCKC/uXYGp8Mloag9DjTO4HLzandkwRBR40NM0Bknk+6oAcKpLMRLy+Ocnl3pw7XlnprVvy4/KGcFeFKz/Tsc7h09jdnUADc0hVBe50R3jqyKa3rvHnvRPMX4kzmwuI4CvWkgi3zMtdvHKbW1G2U2X0eCGN2xhqCh2IRhNnQcwmPZwbNCs5zIPP0EwUL3qVL/XXllCuc+F1pCStK1i3gSaN706Y0Y/eBmyQ0w6FqXrzLpxN3+Gomm8C5/ZhhVmLgjfz49rDHHRTEwz33suxHWei6BqDBd+qgq/+sthdCtxlHicCMfiiKo8/+RERxSTSovgczvBGENLSBn0PWsa6rRJulUWc1lQpO8NhmAk2RU5JVT63UlbePkYn4kCdY7Z8c3ad1wT/S7IDglRVYPTISAW781gHuj63N4TQ12ZB5PLPGjqiFizCPOYDBNgdObiDRj2GWU6ZaN+tc/d2wLP3AI4eLILD24+gJ6YhtpSj5XspjNmlYWMxHT87URoxEl42w+24dE/fWyUK4V1rMZ8dRiM5W6RocrvhiMhKScS47ONebUBrDNWAP7W3IWYxmfebgcvjTlYf+pEiRn7siQmddiSJRGSKMAj8+MkXpeEuC5ZS+4uh4hILA6XQ0JVoPdC45UlRGM6wrE4VI3hsa9/OuXMMBV+VI5vA+iM/388zgbs1pX4PglGVHxn7kQ0nupGW7fCq5AxXtFO043VBa8LXVG+OmMmLTolAb4iB1yiiLCq8Q5wDhFt3TGUeZxWG1IzcdBcsShySRBEYdjNE0aS9QykTsw0b44SVyLMbRNB4M1X/EUOtBq/F16Xg+dgJEi8cbdOKhwPIqrG+TE74x1qPgdOo/OboulG21y998ihwLcOJFHAS+8cS0rqqvS7jT7XOjSmozUUhRhwIxiJp/WetR7fIKdNUnWMM0sJm4148lFQJPEG4y8HT+H5t48gZlQpNJ/LfI4PoECdc3Z9syaO62SIVzdSVA3xhLZ+AwVpUeAXilNdCqaWe+AvcqC9R+2t1iXAqoyViAGIxnUcOR3GRL8bFT4ZjPHlUlXT0RXToLSHMcHrAgT0m0UIRvnV6iJ3RrMoU2K2Lj+C1f8x86x2xhsjGP2r+842dJ3B53bilgtmYscn7XhzfytOmgk9DCmLzgxloCXF+bUluP68MxEocqE9HLN6/baHY9Ys3Jtw0RcgwO0U0RlhmFXFE3u2HTiV1jaBuUdd7pXREeaFcAar9J24bK3pDP/xzjHE4hp6Ypo1s2Qag+yQMNEvw+d2otznwslg1PpZcZ2ho4cn6bmd/BxzxKiq1qWo0HXAITLoRka9JPSeNBju9pGuM2z6sCXjrGcg+ffnWAevrsaMmXLinQvPIubL926XaP3eAIBL4gVZrGIhDiHpxt38GWt/uxtBHYBgbEcIsJ4Dr0viv2c6w+ke1XodzP7vUaNbV1NHBJU+2ZooFMsOoyaCgqjKu3r1bbmbDcMpyJRL5g3GvNoAzq4tsd34KFDngV3frH3H5ZEdiKqalSlszjDNwAv0nsnlx0h4ycywUQJSMo4NMTDog9RvZuCz7Vhcg2LU89YZwHSGqCjA53aAMSTNosyfzRgvspJpC7rEJKKJftloZjDwuq6m8YtjTE++sao/dLrf2dZKv4wvz6vGGRXF+HRdCeZNSi+xqa90C9iYUs3CzRtBSeSz3Bt+/W7a5/ePtYcRisaN2Vb64y6WHeiJaWjqCKPC54YoCDhlLFnrxuvZ1q1YwSIY4QG4OiDD7ZQQjMSsPIhAkcvql26eDVaNahSiAHjdEiTj5mm420f7ToSsrOdTXQriGs+rSDxfr2PgrGfTkunl+OlXPoU1v3mfL2cbJwHM3xmd8d+bU10KT1BS+emFCV4XlLiOj0/1JLdvFYAyryvpxn3J9HL8w7xqPPvXT5JqkUvGc9DVp3KcYDzXqrkVY9w3hGNxOCV3v9fLK0sIKxpO98TwvS+chdWLh86WH67hvp9zzY7jo0CdJ3Z8MwDAojMnwCs7sPtoJ5gAnF0bgCgIeLH+CDa8fxyAefFixnES0dhvY2A6EDZmBGYQ5bVyB+/QZGo39rwdfIoOp0OEqhlLj8VGI/eEHDxzOc8hihkn4SVm0ioqz3TtW1QkkaozHGkPI1DktG6sgOSkuJimozWkoCUUxZ6mIEo9I99HT7cqHTDwjWB1QEZrl4LmYDTt8/vbD7bhl28dgsaGF6RLvQ50R/me+KSSIoRVfqOQyKy93dQehmRUnpNEwOPiSXOtXbqV8R2MqHA5eCvUvueNzXyJUDQOt0OEJIo4uy51mdBUzCStSp8LLodoLVkzowmNmYcwUNZzokCRC0UOEb6SIsQ03shBh7FtoDOrYcWx9ghKPS7MqfHjvLPK8fRfDgMKAOP3RTAzzfrYfrAN//O33tm/aLSk1XSGzogKgfEsf/O2mCX8P09E48llHT0xdEXjKOlzM2O23PW6JHxmSmna16PhlgQdzvs5H+w2PgrUeWS3N8Ngpf1WL56Ktz4+ZfWFbjXKhlpHhMyLC+NZk7JThKbxwNf3qNJQ4jrfg64O8BlOOKah02jzaJX7TNiXdDtFROOZJeElZtKe7olZNcUHE4vruOH8abhy4RToOsNXn3ob7T0xVBTLUDUdzZ3RUdlHHw7zhuv9Y50QGKyiFs3BaNrFJszVhh4lbnRPG/yZMVd5AV7OU2dAlZ8vr57qikJHb/1y8+sk4/x6XDWynZ08SHeGVUTU3gYjSlzDic6odUY9rvW/cdB0hnBMgyTqOO+s8rSDTGIimDmrTCywk07Ws6k9HENcB0o9DhztCFvHfeJa/wS8Uo8Tv1r9OXz7hV3QdIYZEwevkw0A615rQHNIsbLFNR3QwXqrsoHf6DKdWb8v5o8VAJQX84plwYiKUERFoMg54jwZu5QEHcsoUBMAQ1dL++lXPoXpE31WeUJRLOIl93QGSeT9tF0OEd2KBkEAfMYF72QolrLm9FAckoBiN++r3dQRRiyuw+ngF2g+++o9PgEg4yS8xM5Vp/t06hqIqjP8/E8HEFU1/GFvC/Y2dQKCgEhH2Dp+5DIOMTOdJwSVOZ3oVjLfRx+OvhdOAPC5HTjdE0OFb+jz+/NqA9B1hv/efcLqW631Od6VSmIgKnJIYDrvRRyJaUaTCxFMRFLTE/7zzeMwfPn1k9NhRNQ4NJ1XIus9IMf/t28v7MTkNdkhQnaKePPjNnx76ZlpPc+pEjx5Upc0rKxnoH9jD0Ho3xTFfK4OtfXg53/+OO062R80deJvzV1WwpsIZt1YJj4lJR4eiAXAyKXgz52m89/RmM7gdzvgckgjzpOxS5XFsY4KnhSwVBW9Mv13hqqW9tSbh5J64YoCr0EsCbwJAL9YMOvi1NYTw9H2CGKaNnS1ixTiGkM0xmc4NYEiSJJgBb+4MQOuNpp+pFOFbCBm56rWrqhVmjMdnWEVD7z+EQ60hIwKWbwdnmYs8/NKVrx3tqYznAhGEYrEsedYp3HWOrvM98L6rQdxy39+gL+dCEIQBIRjcXSEFRxq60EwoqKpPZyyO1ViMQezCM1Pfr8P7eGYtW8rQIDLIQz4ckoJM+rTPTFEVA1H28M4HoxAN8qaSoIAp0O0Vlk0BivKelwOtPfE+BnxxFneEI/dIQpWNnNVwI0Kn3tYRYOG2x52MGbQD0biVgLiQHQGbHi3Ka0iIG09Cn6z8ygvNWpUIxNFweg73vuaiOA3O7JDshLjeIEco/WpwBPU5tQE8MBX52dcKAiwV5XFsY5m1AUqm8tN6VZLM3vhrnutAftbunklH2MmBOPMaZXfja5oHCe7FCsRxykyCGLyXf9QeF1xHYAEp0NEudeF2y+cjZZQBK/vO4mTwQjCqganpo8oCS+xc1U6wzNnbzrjRUM0nWdA633uR/qWI+Vfz4tf/PNL72d1ppH4XjjVrVgzp2CEB2TeLUuHqvEiJMc7wphU6rGObgG9x4DqD53GhneboMQ1FMsOBKP8yJIOPn6X0bM6VV9qM+aK6E3E0nWGmHHuWmCAUxCsI0ouh4iJfhlxTUdrVwzhGM+Udjp4e05NSO+8Nt8q6c1uziRfIVsJnmbQv+U/P0CXMnSt79M9CkqKXEPWVejsUdHUHgEA8H45ulV4yCGKcEq8nzeDudIk87r9GoMoMGiMwSVJ6Iyo8Lkd1mNaMq084zyZga4b5skNpySgoTmEvceDaR8FJKlRoC5A2V5uGk61NKcoIBSNG92xXJAdIlpCUURVHYqqQ2MMPTHNOLJlJLHovJylSxIQS3PWal6AzD2zWVXFOLPCi7JiF5ZM44+tM6JmJQmvrsyDIidfth9K39ELAj8mxlJ8biDH2sO45T8/wANfnY+lZ1UMd7hJEt8LkrGPLAq9R+GcRl1yASLi4ME1rvEjQV5Zss4hn+qKQoCAX711CKrOM5ZDkXi/mxc1rkN2ipBY8o2Xca8GUeDL/vxGiz8rZrCNawwC08DAZ3ZVATe8Lj6LrSsrwidtvIMEY+b/pIe/xxi8Lslq2JJJvkK2EjyXTC/HA1+dj289+86Q73dNB0/uCquD1lVoDkb6BX7zaVI13SoX65QEBKMqSjwuVJe40RriiXEA4HGJmFOTfNxqJHkyqa4b3UrcanvLk0gZ7ty4F//2D4NXvyODo0BdYPouN2WjA81wu9/0KHHUlvJqYhHjbKzTKFnZElQQ13jCj2Cco+VJRW6UePjxGrOq1GAcogAIzKh7PfCRomwk45V5eIGXsKLB4eDJTSkaiKUkiXxJse++a1+J+6gaA1qCUaz5zft4/OufzjhYm++FjnCMbxUYx9oSZ6G83CmDIAhwiAJvVSkAUTWOsKJBFHmil1nrmZ/H7b8iYGLov8fsEPmqS2c4ZjQF4Y+WGQl1ekKwUnV+w1Zdkrxt8dXP1uHJrY2I6zqicQ2DnOYbkNmzeSRFg7KV4LlkWjkmFMtoDkaH/NrPn1WObQdODbhffP15Z+LBzQcA8Bve3qptvasYqlHp7cpFU3CwtZuvtOm8M1ql34cVc6uwdHp5Vk+W9L1umGVNNeN1NzMLjndGaL96hChQF5jhNPVI94KTbrU0oH/3m97lb15vOGZcRSSjaIRkZGg7JL5P5jGKcCQGrlQkUUBY0TI6UjRcc2v8qCvzoCMcAxjgEkUoeurAm3h0y1x6FCEARqJbqviW6rFKIhCKqLjtd3vw0KVnZ/QY9p0I4W8nQugxVgJEgR/LSfxZZolOATwISeAzICWu43RPDB6nCI3x4OlzOxDt0vqvGhh/zNipsd6GH7JRAc18n1h7z8YNmmbcxJn7tfwMPv9ar0uylpZ9bideePsTABJiXTqYwL+273aJGWP6Ps/mCs5I8hWyad+JkFWbfjAOScAln6nFirlVAy67+9xOtIaikB0SVE23+mz3XXQ4s9yLu748x/r5o33sM6maoY/f8GmMj513egPcTgcmlbiTstfzfQS1EFGgLjCj0dQj3WppqbrfmMVOGBI6RiUeo0LvMjYAa0+7zOvimbEJPZcF8NmZxyXhXy6YiXMml+CB1/cP60hROlKd+bx1+Qx85/ldUFQdTgd6Z58J+gbcxBsaSRAgGsG6b3BJfHzWc258b4+RcJPJBex0t4JQVO3d1wUPjH0v4DpjAGNQjb3rMq8LUVXDRfNr8Pahdpzs6oIgCGjrjiXdhJivI2B0EQMv+OKRJfzLl2bglT3NVgW0qKr3HgdiuvXc8cp0InQwOCSgrrQI7WEVk0qKcM+qeVYRGF1nOLPCix2H26EbNxO84lb/mx+nkRRhBkLz3LCq6VmvpJUps8Ka2yEgmlCC12Q+pEklRdZzMNCy+7YDp/g5b79sHf1zSqKx9M2TFQUA/+uztdZ7KBfHPhOvG8c7+faXxNMLoGl8+6TCJ0MUxIwLEhGOAnWBGa2mHpl2v3E7RcgOERGVd3oyE3pUTQdEXuDBPOvMGM+k9RU5oTNgWrkX0biOcIzPCAUw9CgazqgoxpULJ6OhpQuHTmV39WCwJLxbLpiBh944gFict3+UhD5NI4wMWokBHllCj6JB1XgiU2+Q4l/qdojWHm1cTw58ojFFFQD4ixwZX8A6wip0nZepNPN+HZLYb2la0xlU4wNqXEdzMIoil4RN+1oQiWnGDZLxOI2bDHMWbv43Y/xTRS4JbqeEaRN9uH2FP+HmzgGXJFolKvlYeJBmxtEgt1OCR3ZAFEV09MSsM9KAmdRXjbcPtQMJqwBSn6Vzc2mfL6uLqCmR0RmJ9wv8+WaWdPXKDqh63Krsl0gUgO98/syk5yDVe8D8nXdJolXmU4n3tlOVHRI8LglLp48s3yET5nXjnj824G/NITCNF2FxOyVU+Hpb3uajK+BYQoG6wIxmU49Mut8Ixlnm4x1hqBq/GFf6XTjeEUUszpe8J3hlROPm7NyBKxdOxos7juJkVwwlHidcDjEp6eVYew+uee4dLJk2IaurB+kk4T191efw4OYDOHq6BzoAtySgKlCEs+tKcEZFMQCGR974GKGoagWUmJF8JQg8aE4slqHGNXRE4kmzQbOdIU/64jcwftmBUz2xjC5gJV4nn40yZnTz4klacIhJZ9fNMTiMVogArykdiWmY6JMRUflpZUkQ4BA1a0UgcWauGYHR3Ac2m5Dcs2oenth6EB+1dCUl1IkCjBsdZiS48dmVgIFrcdeV8Uz0uJEdb7a77FuJTNUY3A4BE4pldCs6Soqc+Ld/mG2bzOLtB9vwxNaDCEZUqJpudLVKnk+LIm8xesWCyUP+e8m/dzK85R6rIIsk8OSx2dX+vHR1Avh142er5uE7z+2CUxJ4ZTlXb8MQIL8tIscCCtQFZrSbemTS/UYSBbidDoiiBo9LQjimI1Dk5L2oBaQ8RjW3JoD12xrxtxMhdIZjYODdhCp8MlwOEQ3NXTjY2g2dsaysHqSbhPfcNQuw4YbUR1bMQG/2AOaJV4Jx/poXoQB4DWtzFm0GGGuGaHSgMou1xIyVi0wuYOVeGX63A6FoHKpxRMncT5aMs7aJtabNbQiWMK7WrhicDl7IRJD4jDzeJ5NOAL+pqPC50a1oKW4E+YzeKfEWqbxCWJzvSaeYXQ30upV5XPC6JHhkF8AEdCtxowiNAKckQNN0mP1SYhpDVNX6ZTHnW+LNYIXPhVNdilHRjVcKCxS5eG36Iifu+PvZaXek6vd75xABDdbNb7735OdNCmBWNS+IVOZMDtL5bhE5FlCgLkB9l6k7jb26Kr8bly+YbJUbzMXPNpfIz64LJHVzKvO4MLvKh4aWrpSz8yXTy7Fgahm++tTbUDUdFcUyb1FoBNAqv4jmIE9O6QjHkoIrMPxf/uEm4fW9WUkM9JPLPEYbQ6OMqnEsKhbnBVrKvDJP2NI0NHfyVoMArJ7KbiPoeZwijndGUVtaBJ0xaxk7XXNr/JhTE8AHx4LQdD2pj7LbwW9s4jpDhY+XNm3vjkEXGCSjfzPAZ8owzoDzZhQCnAn785IooLJYhkeWEIzE4XWJWDG3Cm8dbMOx9jB++dYh9PRZoWjvURCL8/PWVX43ioxjYEO9bn1brbaEeNEQh8TvLpggwOsUMdEno61HRV2ZB89cfS4cjtQrLrmW6mbQ5ZCs90lcZ+hW4jh3ahluPD87XdTy3cjHZNeugGOFwNgwDiyOQ6FQCIFAAMFgEH6/ve4GdZ3h/+48it/sPIrWEG+Vl6s6u8Mtwp/K3qYgrn9hF7yyA25n/xlzRNXQ0aPA5ZCgaizlL3+6Wd/bDpzCrb/9AJU+OeU4dZ2htVvBg5eejWUz+u/1pRprYktO3v1Lx5nlXngSCokwxnDkdBiKphn9h53wyw50RlWjbafRtcglZfS6mTO4rmgcRS7eQYrXF9fgEAVE4zomBdw42hFGxDhfzMDrlZu/+JJx9lkSBShxHbqRsS07efEQp0OESxIxoZjPgE9387KwwagKnTFU+mRMKJaTgrFZla5YdqDE40r7dTMfT2dERXdUNbYU+JE5SRBQU+qGQxCtvtpPX/052yx5D/R+Nt8nPbE4VE3Hr64+N+MxZ+P3bjQl5YAYNxNU93vkaEZdwOoPncbTbx3KS53dbJw3TSeDXRRFXLV4KrY3to1oJjHSJLxUY7VqQsf4BdQ8epRIEARMDLjR0aOgrsyL1lAUx4NRdCu8C1SV342SImfGr1vfmZai88cxp8aPFXOr8MSWg1bdaYdRShKst2EDwF/LuM5QU1KEcCyO1i4FDlFAsUuCIIio9MtYcEYZ/vxRK3qUOGQHPzNr1rBuDiroDKuoChShWOb12Sv9Mjp6FNSWetAaiqb9upmP52d/bEBDMy/wIYA3XymWnWjrikGJa1ZN9X/buBd32qSYxkDvZ/N9IjtEtHYr6IwkFy4ZTvC1WyOfvuzaFbDQUaAuUKNR+CTX0g2eS6eX4/rzzsS+EyGc7lbQEVZR4nXC53amvVw80iS8wcYaN8qIJh5DS2TecPzzl85CmcfFj7N0RDCp1A3R6Ns5ktdtoIsjALy+rwUfHAsmtE7kgSMxm1oQ+HGazjDv/wwAlX7ZKm15MhTFb3YehUviR7vMLlaJoqqeVJo08TGXe+VhXbTNYP3t596BSxLhcTkQ13WcMI4mSaIAQeKJcU0d9immkcnN4FjsPGX3m4lCZI/NnTR0dHRg9erVCAQCCAQCWL16NTo7Owf8elVV8f3vfx/z5s2D1+tFTU0NrrrqKpw4cSJ3gx5Fw9lztSszePJjRjoiMQ1dURWRmAZd58uk0yqLrYt7V1TFr/56GA+8/hFu/889uP6FXbj6mZ3YfrBtyJ810sYLiWM1d4sY+BJzVNWMs628hGVf5gW63CtDFAR09MSs86WJRvK6mRfHZTMqMK+WH1EyH7NXlnj2NWNgYEaWOD8r7naK0I3s6lCUlyGdXOZBmVe2GiwE3E6jwYhuLNcbBWzMcRv/r+nAqS4FDCzpMfcdVzrmTQpgdrUfMY1BdvIz3ok/lxfTEDGpxG2b5g+p3iMm82bQfD8Dvcv8Dc0heGUHKn0yvLLDWllJ531Nxoe0Z9T/8i//kvY/+vDDD2c0mMFcccUVaGpqwqZNmwAA1113HVavXo1XX3015deHw2G89957uOuuu3D22Wejo6MDN998M1auXIldu3ZlfXy5NhqFT3LNDCRrf7sbB1q7k44DCQLv15uUuPRmI3piWsbL/CNJyOmbLCM7RHSGY1aGNwDENA3d0Th8bqf1fX1n628dbMvp62bWnV7zm/cRivSeuzYzsc2EtjKvC6FIDCUeF4pcyZcFjfGCGjGNQYDOm3wAEASW1O9YFHnGe0TREIzGR5Tl27+YRhyi0bLR3K+u8LkhivYppjGchKqxsCJGciftQP3+++8n/f3dd9+FpmmYOXMmAODAgQOQJAmf/exnsztCAA0NDdi0aRPq6+uxcOFCAMAvf/lLLF68GPv377fGkCgQCOCNN95I+tgvfvELLFiwAEePHsXkyUOfX7Sz0Sp8kl/MWqLVGT968vM39kMURISMxKVJJUVWok4mF7WR7KGZgX7daw34W3OXdTzL6xJR5BTRHlZxtD2M6kARSoqcKS/Q+Xjdlp5Vgce//mnc9rs9CCtx+Iuc8LkdiGnMOst+6efq8H/+chiyo/+YzOpzutF8xCHwA1lmYZukkqU6Q1u3glKva8RZvoPtV1f43LYsppHuzeBolAImY1fagXrLli3Wfz/88MPw+Xx47rnnUFpaCoAvTV9zzTX4/Oc/n/VBvv322wgEAlaQBoBFixYhEAhg+/btKQN1KsEg79FbUlIy4NcoigJFUay/h0L2XDoezcIng8lm1qk5q9B0hhkTi6GoDHHjmNGpkAJVY4jEdEz0O9ERVsAYcKIzikmlgnWRHs5Fre/YPz+9fNhjX3TmBASKnPDJEgJFLjglXnVNEAQUu1Uc74ygrVtBLM5rMve9QOfrdVt6VgUeuvTshHaYsX71pF94+5OUNxBulwinJCEa1yCitzysJApgjB/lSjwzfkZFMW5fMXNEe6zma6XqDN/6/87APX/8m1GBywHZKUBRGbqiKs8JEDI/iz4a0rkZHAsrYiR3Mkome+ihh7B582YrSANAaWkpfvrTn2L58uW45ZZbsjZAAGhpaUFlZWW/j1dWVqKlpSWtfyMajeJf//VfccUVVwx6zGrdunX40Y9+lPFYcyUf5xaznfiSOKsQBRFFLoBBxCdtYTAATocAVdcRjesABDgkvux5qisKr8trBbl0LmrZGvu+EyEcOtWDCp+735Eyn9uJyWUCghEVa74wHZ+ZUtrvAp3P86aDBRBdZwPeQIABLocABl7LnLdVFKxSnk4RKPe50aNoOLPCi99dv3hEZ5tTvVYaA7oVDS6HiJbTMauEJi8kwqt82amYxlAJVWNzRYyMlox+m0KhEE6ePNnv462trejq6kr737n77rutMpQD/TH3k/suDwGwyiYORVVVXH755dB1HU888cSgX3vHHXcgGAxaf44dO5b248k1c5ltdrUPYSWO1m4FYYXvDWY7C3Y0El9SzSqiMR1KXOPtIyFY+9aCUSzbYZz1NfstA0Nf1LIxdl1n2NsUxLYDrQjHNN4hKAW3gxdtmVrhHTB5KpevW1+pks7Mj/cm20XRGY4hGImhMxxDS4h3LrvlghmoK/NAZ3y/Om6ctxYEET2KhjKvE7evmDniIJ3qtWKMoUdRceR0GJFY3OgGxmf3ms7Q2qWg/tDpLD1Lo2+4iWdkfMtoRr1q1Spcc801eOihh7Bo0SIAQH19PW677TZccsklaf87a9asweWXXz7o10ydOhV79uxJeWNw6tQpTJw4cdDvV1UVX/va13D48GH8+c9/HrJoiSzLkGV56MHbxHD3XDNZuh6txJdUswqzfZ8g9i6xelwSZIeEqKpZpTH58SBpyOXibIzdnOEdPNmF7piGnmgcUVVDVcCdlDgGpD8TsuN50yXTy3Hlwsn4/7c24kRnxCp76nM78YVZlYjrvEZ4sUtCTNMR1/ietarpEEXgyoUjO1I02GtVW1qEj1q6gIQcBgG8SUh5sWxlfhdK8hVV8iLDkVGgfvLJJ3HrrbfiG9/4BlSVJ3k4HA58+9vfxgMPPJD2v1NeXo7y8qF/sRcvXoxgMIidO3diwYIFAIAdO3YgGAxiyZIlA36fGaQ//vhjbNmyBRMmjF5pzXxK99xipsu/o5X4kmq/1kpc0hk0xmtMFxkZysc7IohrvLOVKAiIqNqQF7WRjt2c4bX3xBDXeN1xHUA0ruPI6TAm+t2o8PEbu+HuMdvtvOn2g214ccdRSAJQU1IEURAQjsXR3hPDc9s/4V9kLIOLogDR6hbGG2+88sEJfHvpmRkHl8FeK0VlVkOTKr8bDom/V8z8AIckFlzyld3LghL7yChQezwePPHEE3jggQfQ2NgIxhimT58Or9eb7fEBAGbPno0LL7wQ1157LZ566ikA/HjWRRddlJRINmvWLKxbtw6rVq1CPB7HV7/6Vbz33nv4/e9/D03TrP3ssrIyuFy53/vJZ/m/dDpHDXRhyHbiS+LzsGJuFY62h61ZhcvBL8BRVYNT4kdwBIEnj9WUuHG8MwIBAkJRFS5JHPKiNpKxmzO89p4YoqoGzTh7LAi8gxMDcDIUhblPGolpCBTlv0FCJhJns9WBIgiCgFNdCtp6Yv36W/P+yvxGzyHxhLK4puNvzV34vzuP4huLpmQ0hsFeK2ulReC1v/uuZBRq8pUdV1aI/YyoMpnX68X8+fOzNZZBvfjii7jpppuwfPlyAMDKlSvx+OOPJ33N/v37EQwGAQBNTU145ZVXAADnnHNO0tdt2bIF559//qiPOVE+KxCNdPk3m4kvqZ6HCcUu+N0OnO6OIagzeFwSGBhcksQraOm8gEa3omFSSRG+8/kzUVfmSeuiNpKx7zsRwsGTXYhrfHbvNEpwmi0tzXrZLSEFAni97Loy3mBjb1OwoC68fWez3YqKk11RqzVnqlIims6rhIkCD9gxjeGlnUdxxYLJGT3ewV4rc6XF/O++Cjn5ym4rK8R+0g7Ul1xyCZ599ln4/f4h96E3bNgw4oH1VVZWhl//+teDfk1iUsbUqVP7JWnky0hms9kw0uXfbB0pGuh5aA4q8LpE3PiF6VYADkZieOrNQyNeEhzJ2NvDMUTU3iznfs8devslVwfcKHJJONoexnee3wWvS4IoiAVTEjJxNsvA0BJUrCA9UKTWWW8eAe9nDbSEohkvPw/2WsnO3udfdiS/DtRGkYx1aQfqQCBg/aIEAnT3ly47VCAa6dJ1NhJf0nkeXt/XgueuWdDbCnNa6r7QwzGSsZd5XBAFgKet9WJgiCcU+hAEwejDDIQVDXGdQYSAqRPcUHWWsxsyIPPtlcTZLIsDMaN1Kob4Vl6ZjGeAu41s70yXn4d6rSZ4XXy7wSjSQslXZLxIO1A/88wzKf+bDM4OFYiysXQ90sSXTJ6HbC0JZjr2uTV+TJ7gxZ6mTiNYm20ceztPCeAzakkUcDKkJJ3/jmkMRa7c3ZCNZHslcTbrTaxXnlAiNNXEmoFB1QFJEBDwOAGGES0/D/VaAaDkKzLuZLRHHYlEwBiDx+MBABw5cgQbN27EnDlzrD1kwtmhAlG2lq5HkviS7+chk7GLooBbl8/Ad57fBUXVAUnnxUGMUpoAD9KyQwQYrPPfAoA4Y9YRslzckI10eyVxNtsZUSHAbDzCCeBJXOaRrERFTtE6IpWN5eehXitKviLjTUaVCS6++GI8//zzAIDOzk4sWLAADz30EC6++GKsX78+qwMsdImz2VRykQQz0s5Rff+tTLoh2eV5GO7Yl55VgVsumAHZKSKuM6hx3erSxGfSvO60xnrrlDP0b3kpSyLUUboR6but4HZKVuONKr+cdncpczb7qZqA1XjD5BB5a8zE+6wyjxN1pR5M9PMOVtlcfk71WplFZ94yCtR8fnr5sN6DhBSqjAL1e++9Z9X0/t3vfoeqqiocOXIEzz//PB577LGsDrDQ2aUCUT6rYQH2eR4yce150/D0VZ/D/NoSlHhc8Bc5ITtESKKAmhLeHCLx/HdcZ5Ad/IyvaTRvRLLZ8nTJ9HI8/60FuOuiOaj0ySiWJbgdPMFMjevQGeCSBJxR7oHbKaFLiSMS00b9fbT9YBuufmYnrn9hF2797QfDanFKSKHLaOk7HA7D5/MBADZv3oxLLrkEoihi0aJFOHLkSFYHWOjsVIEon2c27fQ8pKNvUtaSaeXYcENvcpvZdrNb0eCQxAHPfwOjn5Wc7W0FURRwxQLeXe6lnUfREooirvH2lnVlHty6fEZWEv3Sle9TE4TkW0aBevr06Xj55ZexatUqvP7661i7di0AXut7qBKd45GdKhDl88ymnZ6HwQyUlHX9eWciUMRnxGfXluBnq+YlHSEb6Pz3aN+IZLvBQ9/HL0DApFIPvr5gctIZ6Vy8j4ZzagIA7V2TMUlgGRw2/t3vfocrrrgCmqbh7/7u76y+z+vWrcObb76J1157LesDzZdQKIRAIIBgMDjim5B8ViazEzs/DwPN3lq7olDier/z0WbwNh9L4vlv1bgRGe1z1LrOcPUzO41kQblfsmBLSMHsal/S0bfhPv4O42Yj17PXvU1BXP/CLnhlR79uZQAQUTWElThu/MJ0vL6vJS8FhQgZbRkFaoC3nmxubsbZZ58N0Uia2blzJ/x+P2bNmpXVQeZTNgO13dk5gOZCb8ALJc3eupU4mtrDiOsMRU4JUyd4oOpswOCVj+exN8BqKbcV0gmwAz1+YPgBP1u2HTiFW3/7ASp9csqfqesMTZ0RuJ0iNJ3Z4uaCkGzLuIRoVVUVuru78cYbb+C8885DUVERzj333LTaThL7yWeJU7tIlZTFwHCqa3jno/OxvZCNbQU7nPnva6hl/WhcQySmQQBQW1qUl4JChIy2jAL16dOn8bWvfQ1btmyBIAj4+OOPceaZZ+I73/kOSkpK8NBDD2V7nGQUUbION1R/7NE6H52tGfhIkwXzfdY9laFqAJzujkEQgHKffW4uMjHeV7PI4DIK1GvXroXT6cTRo0cxe/Zs6+OXXXYZ1q5dS4G6AJgXhtPdCh75n4/RFVWtrknA+JyRpNsfu+/56JEEr2yvZIxkNp/tpLRsGOq0gOwQwQDIUv/xAoXRVYtWs8hQMjpHvXnzZtx3332ora1N+vhZZ51Fx7MKQOKZ1LW/3Y29TZ2IxHT0xLSkrxvuGdxEZnGKbQdOYW9TcMhiG3aQ6qz3aJ6PNlcyGppD8MoOVPpkeGWHtZKRqzPC5mvV1qOg0u9GRzhmq7Pug9UA+N4Xz4LXJeW1kM5I2OU9QOwtoxl1T0+PVT40UVtbG2RZHvGgyOjpu8ztkASEIioUTcPxjggmlRahWO59W2QyIynUGUKq2dtonY+2Q7MWoP9rpTN+w3asI4wKn9s2Z90HWtYHgNf3tYy4PG4+2OU9QOwvoxn1eeedZ5UQBfjMS9d1PPDAA/jCF76QtcGR7EpVatIl8XKTkiBAYwynuqJJs6lMzuAW8gyh7+ztVHcMHpcE2SnC7XRY56MzKb+aKJvVxDKV6rUq88pwSRKUuI6OnljOK9gNJlVZ0WyWx801O7wHSGHIaEb94IMPYtmyZdi1axdisRhuv/127Nu3D+3t7fjrX/+a7TGSLEl1YXC7RMgOCVFVgyQCSlxHVNVR5JKGPSMZKzOEVLO3bPXHNuUycStVohKAAV+ryWVFaA5GUVfmwc1fPAsTimVbJzcVSiGdvuyYvEfsadiBWlVV3HjjjXjllVfw2muvQZIk9PT04JJLLsF3v/tdVFdXj8Y4SRakujAIEFDhk3G8IwJN0wFBgKrpgIphL3fa8XhPplIlZWWzbGauErcG2oZYMbdq0Neq1OtCayiKCcWy7V8rIL/lcTNlx+Q9Yk/DDtROpxMffvghJkyYgB/96EejMSYySga6MBTLDkwqLUJLMIpYXEMwqsLjlIY9IxnrM4Rsno/OVuvRwQx27O7AyS5EYzpKBwgChfha5eL8ejaPUeXiPUDGhoyWvq+66ir86le/wr333pvt8ZBRNNiFweuS4JUlzKzy4Z+/dBbKvcNf7qQZQvpGu0nJUNsQTZ0RRFQNSlxDkav/ZYBeq/5G4yhdITWqIfmTUaCOxWJ4+umn8cYbb+Bzn/scvF5v0ucffvjhrAyOZNfQFwYHbl8xM+M9vbE0Q8hFAYrR3FsdahuivNiFY7EI2rpjqC2VCvq1yoXRKgpUqPvrJLcyCtQffvghPvOZzwAADhw4kPQ5KiFqb6N5YRgrM4RcHi8brb3VobchJLidEmSHWNCvVS6MdpJkIe6vk9zKuCnHeDFWm3KM5owxKdDlqINUttite1SmMuo6VWCvVa6k+1w+tfpzBZF4RwpPxk05SGEbzcSbQp0hjJXjZUD62xBXGD2mC+21yqWxniRJ7I8CNRkV+eggNVL5PF6W7RWOdLYhVsytwlsH24b988ZbAwlKkiT5RoGaEEO+Zk6jtSc+UD5CdYCX+X1iy8Fh/7xCLQ87EmMpSZIUpoxKiBIyFiXOnFIZjZnTaJdcXTK9HM9dswBPrf4cHrz0bNz4hekIRVQ0B6PD/nmFXh42U4VcppSMDRSoCTGk6p5lGo3uUalqr4uiALdTQpVfRreiYf22xhF3HjO3IT4/vRyv72tBT0wb9s/L1VjtarAOXoWSYEgKFy19E2LI9fGyXO+Jj+TnjaXysJkq1CRJUvgoUBOSYKhz5ovOnIC9TcGsXKhzvSc+kp9Hmc9cISZJksJHgZqQPgaaOdUfOo2rn9mZtUSqXGcTj+TnUeYzIflDe9Rk3NN1hr1NQWw7cAp7m4LQddav93H9odNZT6TK9Z74SH5ersdKCOlFgZqMa9sPtuHqZ3bi+hd24dbffoDrX9iFq5/ZmRR4RyuRKtfZxCP5eZT5TEj+UAnRIYzVEqIk/XKho11CMtclV0fy8wq5PCwhhYr2qMm4NJxyoaOdSJXNbOJ0qoaN5OdR5jMhuUeBmoxLwzlulItEqmxkEw+nathIfh5lPhOSW7RHTcaldGbJqjFLLoREqvFaNYyQ8YACNRmXhlMu1O6JVOYyfldURcDthKrpUOI6ZIc4LqqGETLWUaAeh1IdRxpvhjtLtnMJyX0nQvjbiSAiMR1HO8Jo6ojgSHsPPjndg56YlrSMTwgpPAWzR93R0YGbbroJr7zyCgBg5cqV+MUvfoGSkpK0vv/666/Hv//7v+PnP/85br755tEbqM2Nx+5HqWRSLtSuiVR/OdiGjrAKQQAcoghBABiAiKrjeEcE1QG3tYxPCCk8BTOjvuKKK7B7925s2rQJmzZtwu7du7F69eq0vvfll1/Gjh07UFNTM8qjtDfax0yWySy5byGUfAdpXWd4fV8LAEASBIiCAMH4f6coQGMMrV0KHAKoahghBaogZtQNDQ3YtGkT6uvrsXDhQgDAL3/5SyxevBj79+/HzJkzB/ze48ePY82aNXj99dfx5S9/OVdDtp3hHEfKd/DJJbvOktO170QIraEoZIcEVdMhgkEAH7sgCJBEBiWuYWKA+iUTUqgKIlC//fbbCAQCVpAGgEWLFiEQCGD79u0DBmpd17F69WrcdtttmDt3blo/S1EUKIpi/T0UGhv7etT9aGCFfNzIzF6v9Mto7owirjFIIvjyNwM0jUEAsGLuxIK5+SCEJCuIpe+WlhZUVlb2+3hlZSVaWloG/L777rsPDocDN910U9o/a926dQgEAtafurq6jMZsN8M5jkQKh5m97pJETCotgtspQWcMcY1BZwwuh4QSjwtLp1fke6iEkAzlNVDffffdEIw9tYH+7Nq1CwD6zQIBnp2b6uMA8O677+LRRx/Fs88+O+DXpHLHHXcgGAxaf44dO5bZg7OZ4RxHIoUjMXvd65IwtdyDKWVe1JYWYXKpB15ZwpwaPy17E1LA8rr0vWbNGlx++eWDfs3UqVOxZ88enDx5st/nTp06hYkTJ6b8vrfeegutra2YPHmy9TFN03DLLbfgkUcewSeffJLy+2RZhizL6T+IAmFe0Buau1DlF5NuXszjSLOraR+z0KTMXneIgAYje91BzTJsJp0yr4QkKoimHA0NDZgzZw527NiBBQsWAAB27NiBRYsW4aOPPkq5R3369Gk0NzcnfWzFihVYvXo1rrnmmkET0BKNpaYcvU0otJTHkfJ9HphkjpplFAY6HkkyURCBGgD+/u//HidOnMBTTz0FALjuuuswZcoUvPrqq9bXzJo1C+vWrcOqVatS/htTp07FzTffPKxz1GMpUAN0QR/LaKZmb+l2ayOkr4LI+gaAF198ETfddBOWL18OgBc8efzxx5O+Zv/+/QgGg/kYXsEo9ONIZGCFnL0+1tHxSDISBTOjzpexNqMmhOTeaPc0J2NbQRzPIoSQQkbHI8lIFMzSNyGEFKpc9DQfbZQDkT8UqAkhZJQV+vFIylbPL1r6JoSQUWb3nuaDoWY++UeBOo+oLzQh44ede5oPpG+2utspQRQFuJ0SqvwyuhUN67c10rVrlNHSd57QUhIh40+hHY+kZj72QIE6DwYqfGAuJdn17poQMnKFdN49nWz1IGWrjzpa+s4xWkoihBQKauZjDxSoc2w4S0mEEJJPid3Z+tbGMrPVp1UW2zZbfaygQJ1jVPiAEFIoCjlbfSyhQJ1jtJRECCkkhZitPtZQMlmOFXrhA0LI+FNo2epjDQXqHDOXku7YsAdNHREUuSQUOSUIAhCMxGkpiRBiS4WUrT7WUKDOE3+REy0hBaGoCgBwiCJmVhXjjr+fTUtJhBBCLBSocyzxDHVdWRF0HYiqGsKqhlA0nu/hEUIIsRkK1Dk0UPN4r+xAGWPUPJ6MS9SViZDBUaDOISrHR0gyKqVLyNDoeFYO0RlqQnpRVyZC0kOBOofoDDUhHJXSJSR9FKhziMrxEcJRKV1C0keBOoeoHB8hHG0DEZI+CtQ5RuX4CKFtIEKGg7K+84DK8ZHxjkrpEpI+mlHniVmOb9mMCsyrDVCQJuMKbQMRkj6B9c1qIklCoRACgQCCwSD8frq7JySbks5R6wxOMbNz1FQ0hYxlFKiHQIGakNE10iBLRVPIWEeBegh2CtQ0ayAkWWLt/FKPCy5JREzT0RFWUSxLlKBJxgRKJisQNGsgJNlAtfPdooQqv0i188mYQclkBYBKLRLSHxVNIeMFBWqbo1KLhKRGRVPIeEGB2uZo1kBIalQ0hYwXFKhtjmYNhKRGtfPJeEGB2uZo1kBIalQ0hYwXFKhtjmYNhAyMaueT8YDOUQ/BDueoe8+KaijxOCFLIhRNRyedFSUEANUYIGMbBeoh2CFQA9krtUgIIaSwUKAegl0CNUCzBkIIGY+oMlkBMTtuEUIIGT8omYwQQgixsYIJ1B0dHVi9ejUCgQACgQBWr16Nzs7OIb+voaEBK1euRCAQgM/nw6JFi3D06NHRHzAhhBCSBQUTqK+44grs3r0bmzZtwqZNm7B7926sXr160O9pbGzE0qVLMWvWLGzduhUffPAB7rrrLrjd7hyNmhBCCBmZgkgma2howJw5c1BfX4+FCxcCAOrr67F48WJ89NFHmDlzZsrvu/zyy+F0OvHCCy+k/bMURYGiKNbfQ6EQ6urqbJFMRgghZPwpiBn122+/jUAgYAVpAFi0aBECgQC2b9+e8nt0Xccf/vAHzJgxAytWrEBlZSUWLlyIl19+edCftW7dOmt5PRAIoK6uLpsPhRBCCBmWggjULS0tqKys7PfxyspKtLS0pPye1tZWdHd3495778WFF16IzZs3Y9WqVbjkkkuwbdu2AX/WHXfcgWAwaP05duxY1h4HIYQQMlx5PZ51991340c/+tGgX/POO+8AQL/OUQAvoZnq4wCfUQPAxRdfjLVr1wIAzjnnHGzfvh1PPvkkli1blvL7ZFmGLMtpPwaSGToTTggh6clroF6zZg0uv/zyQb9m6tSp2LNnD06ePNnvc6dOncLEiRNTfl95eTkcDgfmzJmT9PHZs2fjL3/5S+aDJiOWVGVNY3BKVGWNEEIGktdAXV5ejvLyoS/MixcvRjAYxM6dO7FgwQIAwI4dOxAMBrFkyZKU3+NyuXDuuedi//79SR8/cOAApkyZMvLBk4z01i2Po9TjgksSEdN0NDR34c6Ne6luOSGE9FEQe9SzZ8/GhRdeiGuvvRb19fWor6/Htddei4suuigp43vWrFnYuHGj9ffbbrsN//Ef/4Ff/vKXOHjwIB5//HG8+uqruPHGG/PxMMY9XWdYv60R3UocVX433E4JoijA7ZRQ5ZfRrWhYv60Rum77gwiEEJIzBRGoAeDFF1/EvHnzsHz5cixfvhzz58/vd+xq//79CAaD1t9XrVqFJ598Evfffz/mzZuHp59+Gv/1X/+FpUuX5nr4BMC+EyE0tnaj1OPql1sgCAJKPE40tnZj34lQnkZICCH2UxDnqPPJTk05Ct22A6dw628/QKVPTpk4pusMrd0KHrz0bCybUZGHERJCiP0UzIyaFL4yjwtOSUBM01N+XtF0OEUBZR5XjkdGCCH2RYGa5MzcGj+mVRajI6yi70IOYwydYRXTKosxt4ZWLgghxESBmuSMKAq4Ydk0FMsSWkIKIqoGXWeIqBpaQgqKZQk3LJtG56kJISQBBWqSU0uml+OeVfMwu9qHsBJHa7eCsBLH7GofHc0ihJAUKJlsCJRMNjqoMhkhhKQnrwVPyPgligLm1QbyPQxCCLE9WvomhBBCbIwCNSGEEGJjFKgJIYQQG6NATQghhNgYBWpCCCHExihQE0IIITZGgZoQQgixMQrUhBBCiI1RoCaEEEJsjAI1IYQQYmMUqAkhhBAbo0BNCCGE2Bg15SCEjAnUkY2MVRSoCSEFb/vBNqzf1ojG1m6oGoNTEjCtshg3LJtGPc5JwaOlb0JIQdt+sA13btyLhuYQvLIDlT4ZXtmBhuYu3LlxL7YfbMv3EAkZEQrUhJCCpesM67c1oluJo8rvhtspQRQFuJ0SqvwyuhUN67c1QtdZvodKSMYoUBNCCta+EyE0tnaj1OOCICTvRwuCgBKPE42t3dh3IpSnERIychSoCSEFqz0cg6oxuKTUlzJZEqHqDO3hWI5HRkj2UKAmhBSsMo8LTklATNNTfl7RdDhFAWUeV45HRkj2UKAmhBSsuTV+TKssRkdYBWPJ+9CMMXSGVUyrLMbcGn+eRkjIyFGgJoQULFEUcMOyaSiWJbSEFERUDbrOEFE1tIQUFMsSblg2jc5Tk4JGgZoQUtCWTC/HPavmYXa1D2EljtZuBWEljtnVPtyzah6doyYFT2B914tIklAohEAggGAwCL+fls8IsSuqTEbGKqpMRggZE0RRwLzaQL6HQUjW0dI3IYQQYmMUqAkhhBAbo0BNCCGE2BgFakIIIcTGKFATQgghNkaBmhBCCLExCtSEEEKIjVGgJoQQQmysYAJ1R0cHVq9ejUAggEAggNWrV6Ozs3PQ7+nu7saaNWtQW1uLoqIizJ49G+vXr8/NgEeZrjPsbQpi24FT2NsUhK5TgTlCCBmLCqYy2RVXXIGmpiZs2rQJAHDddddh9erVePXVVwf8nrVr12LLli349a9/jalTp2Lz5s248cYbUVNTg4svvjhXQ8+67QfbsH5bIxpbu6FqDE5JwLTKYtywbBrVNSaEkDGmIGp9NzQ0YM6cOaivr8fChQsBAPX19Vi8eDE++ugjzJw5M+X3fepTn8Jll12Gu+66y/rYZz/7WfzDP/wDfvKTn6T8HkVRoCiK9fdQKIS6ujrb1PrefrANd27ci24ljlKPCy5JREzT0RFWUSxL1ISAEELGmIJY+n777bcRCASsIA0AixYtQiAQwPbt2wf8vqVLl+KVV17B8ePHwRjDli1bcODAAaxYsWLA71m3bp21vB4IBFBXV5fVxzISus6wflsjupU4qvxuuJ0SRFGA2ymhyi+jW9GwflsjLYMTQsgYUhCBuqWlBZWVlf0+XllZiZaWlgG/77HHHsOcOXNQW1sLl8uFCy+8EE888QSWLl064PfccccdCAaD1p9jx45l5TFkw74TITS2dqPU44IgJHcFEgQBJR4nGlu7se9EKE8jJIQQkm15DdR33303BEEY9M+uXbsAoF9gAgDGWMqPmx577DHU19fjlVdewbvvvouHHnoIN954I/70pz8N+D2yLMPv9yf9sYv2cAyqxuCSUr9ssiRC1Rnaw7Ecj4wQQshoyWsy2Zo1a3D55ZcP+jVTp07Fnj17cPLkyX6fO3XqFCZOnJjy+yKRCO68805s3LgRX/7ylwEA8+fPx+7du/Hggw/iS1/60sgfQI6VeVxwSgJimg63KPX7vKLpcIoCyjyuPIxubKHexoQQu8hroC4vL0d5+dCJT4sXL0YwGMTOnTuxYMECAMCOHTsQDAaxZMmSlN+jqipUVYUoJs8+JUmCrusjH3wezK3xY1plMRqau1DlF5NWExhj6AyrmF3tw9wa+6wCFCLKqieE2ElB7FHPnj0bF154Ia699lrU19ejvr4e1157LS666KKkjO9Zs2Zh48aNAAC/349ly5bhtttuw9atW3H48GE8++yzeP7557Fq1ap8PZQREUUBNyybhmJZQktIQUTVoOsMEVVDS0hBsSzhhmXTaOY3AmZWfUNzCF7ZgUqfDK/sQENzF+7cuBfbD7ble4iEkHGmIAI1ALz44ouYN28eli9fjuXLl2P+/Pl44YUXkr5m//79CAaD1t9feuklnHvuubjyyisxZ84c3HvvvfjZz36Gf/qnf8r18LNmyfRy3LNqHmZX+xBW4mjtVhBW4phd7aOjWSNEWfWEEDsqiHPU+RQKhRAIBGxzjtpEe6jZt7cpiOtf2AWv7IDb2T8HIKJqCCtxPLX6c5hXG8jDCAkh41HBVCYjyURRoGCRZelk1Qcpq54QkmMFs/RNyGhLzKpPhbLqCSH5QIGaEIOZVd8RVtF3R8jMqp9WWUxZ9YSQnKJATYiBsuoJIXZEgZqQBJRVTwixG8r6HoJds77J6KKsekKIXVDWNyEpUFY9IcQuaOmbEEIIsTEK1IQQQoiNUaAmhBBCbIwCNSGEEGJjFKgJIYQQG6NATQghhNgYBWpCCCHExihQE0IIITZGgZoQQgixMapMRgioZCghxL4oUJNxb/vBNqzf1ojG1m6oGoNTEjCtshg3LJtGTTgIIXlHS99kXNt+sA13btyLhuYQvLIDlT4ZXtmBhuYu3LlxL7YfbMv3EAkh4xwFajJu6TrD+m2N6FbiqPK74XZKEEUBbqeEKr+MbkXD+m2N0HVqMEcIyR8K1GTc2ncihMbWbpR6XBCE5P1oQRBQ4nGisbUb+06E8jRCQgihQE3GsfZwDKrG4JJS/xrIkghVZ2gPx3I8MkII6UWBmoxbZR4XnJKAmKan/Lyi6XCKAso8rhyPjBBCelGgJuPW3Bo/plUWoyOsgrHkfWjGGDrDKqZVFmNujT9PIySEEArUZBwTRQE3LJuGYllCS0hBRNWg6wwRVUNLSEGxLOGGZdPoPDUhJK8oUJNxbcn0ctyzah5mV/sQVuJo7VYQVuKYXe3DPavm0TlqQkjeCazvmh9JEgqFEAgEEAwG4ffTEuhYRZXJCCF2RZXJCAFfBp9XG8j3MAghpB9a+iaEEEJsjAI1IYQQYmMUqAkhhBAbo0BNCCGE2BgFakIIIcTGKFATQgghNkaBmhBCCLExCtSEEEKIjVGgJoQQQmyMAjUhhBBiYwUTqH/2s59hyZIl8Hg8KCkpSet7GGO4++67UVNTg6KiIpx//vnYt2/f6A6UEEIIyaKCCdSxWAyXXnopbrjhhrS/5/7778fDDz+Mxx9/HO+88w6qqqpwwQUXoKuraxRHSgghhGRPwXXPevbZZ3HzzTejs7Nz0K9jjKGmpgY333wzvv/97wMAFEXBxIkTcd999+H6669P+X2KokBRFOvvoVAIdXV11D2LEEJIXhTMjHq4Dh8+jJaWFixfvtz6mCzLWLZsGbZv3z7g961btw6BQMD6U1dXl4vhEkIIISmN2UDd0tICAJg4cWLSxydOnGh9LpU77rgDwWDQ+nPs2LFRHSchhBAymLwG6rvvvhuCIAz6Z9euXSP6GYIgJP2dMdbvY4lkWYbf70/6M1bpOsPepiC2HTiFvU1B6HpB7YIQQsi44MjnD1+zZg0uv/zyQb9m6tSpGf3bVVVVAPjMurq62vp4a2trv1n2eLT9YBvWb2tEY2s3VI3BKQmYVlmMG5ZNw5Lp5fkeHiGEEENeA3V5eTnKy0cnKJxxxhmoqqrCG2+8gU9/+tMAeOb4tm3bcN99943KzywU2w+24c6Ne9GtxFHqccEliYhpOhqau3Dnxr24Z9U8CtaEEGITBbNHffToUezevRtHjx6FpmnYvXs3du/eje7ubutrZs2ahY0bNwLgS94333wz7rnnHmzcuBEffvghvvnNb8Lj8eCKK67I18PIO11nWL+tEd1KHFV+N9xOCaIowO2UUOWX0a1oWL+tkZbBCSHEJvI6ox6O//2//zeee+456+/mLHnLli04//zzAQD79+9HMBi0vub2229HJBLBjTfeiI6ODixcuBCbN2+Gz+fL6djtZN+JEBpbu1HqcfXbqxcEASUeJxpbu7HvRAjzagN5GiUhhBBTwZ2jzrVQKIRAIDBmzlFvO3AKt/72A1T6ZIhi/6Q6XWdo7Vbw4KVnY9mMijyMkBBCSKKCWfom2VHmccEpCYhpesrPK5oOpyigzOPK8cgIIYSkQoF6nJlb48e0ymJ0hFX0XUxhjKEzrGJaZTHm1hT+6gEhhIwFFKjHGVEUcMOyaSiWJbSEFERUDbrOEFE1tIQUFMsSblg2LeWyOCGEkNyjQD0OLZlejntWzcPsah/CShyt3QrCShyzq310NIsQQmyGksmGMNaSyRLpOsO+EyG0h2Mo87gwt8ZPM2lCCLGZgjmeRbJPFAU6gkUIITZHS9+EEEKIjVGgJoQQQmyMAjUhhBBiYxSoCSGEEBujQE0IIYTYGAVqQgghxMYoUBNCCCE2RoGaEEIIsTEK1IQQQoiNUaAmhBBCbIwCNSGEEGJjFKgJIYQQG6OmHEMwm4uFQqE8j4QQQshY4/P5IAiDdy2kQD2Erq4uAEBdXV2eR0IIIWSsSaeFMvWjHoKu6zhx4kRadz2JQqEQ6urqcOzYsTHXxzrf6LkdXfT8jh56bkdPoT63NKPOAlEUUVtbm/H3+/3+gnrTFBJ6bkcXPb+jh57b0TMWn1tKJiOEEEJsjAI1IYQQYmMUqEeJLMv44Q9/CFmW8z2UMYee29FFz+/ooed29Izl55aSyQghhBAboxk1IYQQYmMUqAkhhBAbo0BNCCGE2BgFakIIIcTGKFCPwLp163DuuefC5/OhsrISX/nKV7B//37r86qq4vvf/z7mzZsHr9eLmpoaXHXVVThx4kQeR10Yhnpu+7r++ushCAIeeeSR3A2ygKX7/DY0NGDlypUIBALw+XxYtGgRjh49mocRF450ntvu7m6sWbMGtbW1KCoqwuzZs7F+/fo8jbiwrF+/HvPnz7cKmyxevBivvfaa9XnGGO6++27U1NSgqKgI559/Pvbt25fHEY8cBeoR2LZtG7773e+ivr4eb7zxBuLxOJYvX46enh4AQDgcxnvvvYe77roL7733HjZs2IADBw5g5cqVeR65/Q313CZ6+eWXsWPHDtTU1ORhpIUpnee3sbERS5cuxaxZs7B161Z88MEHuOuuu+B2u/M4cvtL57ldu3YtNm3ahF//+tdoaGjA2rVr8b3vfQ///d//nceRF4ba2lrce++92LVrF3bt2oW/+7u/w8UXX2wF4/vvvx8PP/wwHn/8cbzzzjuoqqrCBRdcYPVtKEiMZE1raysDwLZt2zbg1+zcuZMBYEeOHMnhyArfQM9tU1MTmzRpEvvwww/ZlClT2M9//vP8DLDApXp+L7vsMvaNb3wjj6MaG1I9t3PnzmU//vGPk77uM5/5DPvBD36Q6+GNCaWlpezpp59muq6zqqoqdu+991qfi0ajLBAIsCeffDKPIxwZmlFnUTAYBACUlZUN+jWCIKCkpCRHoxobUj23uq5j9erVuO222zB37tx8DW1M6Pv86rqOP/zhD5gxYwZWrFiByspKLFy4EC+//HIeR1mYUr13ly5dildeeQXHjx8HYwxbtmzBgQMHsGLFinwNsyBpmoaXXnoJPT09WLx4MQ4fPoyWlhYsX77c+hpZlrFs2TJs3749jyMdoXzfKYwVuq6zf/zHf2RLly4d8GsikQj77Gc/y6688socjqzwDfTc3nPPPeyCCy5guq4zxhjNqDOU6vltbm5mAJjH42EPP/wwe//999m6deuYIAhs69ateRxtYRnovasoCrvqqqsYAOZwOJjL5WLPP/98nkZZePbs2cO8Xi+TJIkFAgH2hz/8gTHG2F//+lcGgB0/fjzp66+99lq2fPnyfAw1K6h7VpasWbMGe/bswV/+8peUn1dVFZdffjl0XccTTzyR49EVtlTP7bvvvotHH30U77333rDaj5L+Uj2/uq4DAC6++GKsXbsWAHDOOedg+/btePLJJ7Fs2bK8jLXQDHRdeOyxx1BfX49XXnkFU6ZMwZtvvokbb7wR1dXV+NKXvpSn0RaOmTNnYvfu3ejs7MR//dd/4eqrr8a2bdusz/e9JjDGCvs6ke87hbFgzZo1rLa2lh06dCjl52OxGPvKV77C5s+fz9ra2nI8usI20HP785//nAmCwCRJsv4AYKIosilTpuRnsAVooOdXURTmcDjYT37yk6SP33777WzJkiW5HGLBGui5DYfDzOl0st///vdJH//2t7/NVqxYkcshjhlf/OIX2XXXXccaGxsZAPbee+8lfX7lypXsqquuytPoRo72qEeAMYY1a9Zgw4YN+POf/4wzzjij39eoqoqvfe1r+Pjjj/GnP/0JEyZMyMNIC89Qz+3q1auxZ88e7N692/pTU1OD2267Da+//nqeRl04hnp+XS4Xzj333H7Hig4cOIApU6bkcqgFZ6jnVlVVqKoKUUy+/EqSZK1kkOFhjEFRFJxxxhmoqqrCG2+8YX0uFoth27ZtWLJkSR5HOEJ5vU0ocDfccAMLBAJs69atrLm52foTDocZY4ypqspWrlzJamtr2e7du5O+RlGUPI/e3oZ6blOhPer0pfP8btiwgTmdTvbv//7v7OOPP2a/+MUvmCRJ7K233srjyO0vned22bJlbO7cuWzLli3s0KFD7JlnnmFut5s98cQTeRx5YbjjjjvYm2++yQ4fPsz27NnD7rzzTiaKItu8eTNjjLF7772XBQIBtmHDBrZ371729a9/nVVXV7NQKJTnkWeOAvUIAEj555lnnmGMMXb48OEBv2bLli15HbvdDfXcpkKBOn3pPr+/+tWv2PTp05nb7WZnn302e/nll/Mz4AKSznPb3NzMvvnNb7KamhrmdrvZzJkz2UMPPWQlRpKBfetb32JTpkxhLpeLVVRUsC9+8YtWkGaMJ/D98Ic/ZFVVVUyWZXbeeeexvXv35nHEI0dtLgkhhBAboz1qQgghxMYoUBNCCCE2RoGaEEIIsTEK1IQQQoiNUaAmhBBCbIwCNSGEEGJjFKgJIYQQG6NATQghhNgYBWpCCABeL/m6665DWVmZ1TP95ptvztnPf/bZZ6lPOyEpUKAmhAAANm3ahGeffRa///3v0dzcjAMHDuAnP/mJ9fmpU6fikUceSfoeCq6EjD7qR00IAQA0Njaiurq6sLsMETIG0YyaEIJvfvOb+N73voejR49CEARMnToV559/vrX0ff755+PIkSNYu3YtBEGAIAjYunUrrrnmGgSDQetjd999NwDeWvD222/HpEmT4PV6sXDhQmzdujXpZz777LOYPHkyPB4PVq1ahdOnT+f2QRNSIChQE0Lw6KOP4sc//jFqa2vR3NyMd955J+nzGzZsQG1tLX784x+jubkZzc3NWLJkCR555BH4/X7rY7feeisA4JprrsFf//pXvPTSS9izZw8uvfRSXHjhhfj4448BADt27MC3vvUt3Hjjjdi9eze+8IUv4Kc//WnOHzchhYCWvgkhCAQC8Pl8kCQJVVVV/T5fVlYGSZLg8/mSPh8IBCAIQtLHGhsb8Zvf/AZNTU2oqakBANx6663YtGkTnnnmGdxzzz149NFHsWLFCvzrv/4rAGDGjBnYvn07Nm3aNMqPlJDCQ4GaEJJV7733HhhjmDFjRtLHFUXBhAkTAAANDQ1YtWpV0ucXL15MgZqQFChQE0KyStd1SJKEd999F5IkJX2uuLgYAD8KRghJDwVqQkhaXC4XNE0b8mOf/vSnoWkaWltb8fnPfz7lvzVnzhzU19cnfazv3wkhHCWTEULSMnXqVLz55ps4fvw42trarI91d3fjf/7nf9DW1oZwOIwZM2bgyiuvxFVXXYUNGzbg8OHDeOedd3Dffffhj3/8IwDgpptuwqZNm3D//ffjwIEDePzxx2nZm5ABUKAmhKTlxz/+MT755BNMmzYNFRUVAIAlS5bgn/7pn3DZZZehoqIC999/PwDgmWeewVVXXYVbbrkFM2fOxMqVK7Fjxw7U1dUBABYtWoSnn34av/jFL3DOOedg8+bN+MEPfpC3x0aInQmMNosIIYQQ26IZNSGEEGJjFKgJIYQQG6NATQghhNgYBWpCCCHExihQE0IIITZGgZoQQgixMQrUhBBCiI1RoCaEEEJsjAI1IYQQYmMUqAkhhBAbo0BNCCGE2Nj/A/pMyjM3As/sAAAAAElFTkSuQmCC"
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can confirm this with a Breusch-Pagan test:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Conduct the Breusch-Pagan test</span>
<span class="n">names</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'Lagrange multiplier statistic'</span><span class="p">,</span> <span class="s1">'p-value'</span><span class="p">,</span>
         <span class="s1">'f-value'</span><span class="p">,</span> <span class="s1">'f p-value'</span><span class="p">]</span>
 
<span class="c1"># Get the test result</span>
<span class="n">test_result</span> <span class="o">=</span> <span class="n">sms</span><span class="o">.</span><span class="n">het_breuschpagan</span><span class="p">(</span><span class="n">lmm_inter</span><span class="o">.</span><span class="n">resid</span><span class="p">,</span> <span class="n">lmm_inter</span><span class="o">.</span><span class="n">model</span><span class="o">.</span><span class="n">exog</span><span class="p">)</span>
 
<span class="n">lzip</span><span class="p">(</span><span class="n">names</span><span class="p">,</span> <span class="n">test_result</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[13]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>[(&#39;Lagrange multiplier statistic&#39;, 96.27687606428948),
 (&#39;p-value&#39;, 8.889448381522433e-17),
 (&#39;f-value&#39;, 11.972698618036382),
 (&#39;f p-value&#39;, 7.474758802932374e-18)]</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>With p &lt;0.05, we can reject the null hypothesis and conclude that there is still heteroskedasticity in the data. Unfortunately, the <code>mixedlm()</code> function in <code>statsmodels</code> doesn't have a way to deal with this, despite the fact that <code>statsmodels</code> has provided the <code>ols()</code> function with a way to do so. While our estimators will not be biased by this, this means our standard errors will be incorrect.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Conclusion">Conclusion<a class="anchor-link" href="#Conclusion">&#182;</a></h1><p>While there remain some problems with our data, we are still able to draw some conclusions. The first is that while energy consumption has a clear correlation with GDP, rail cargo volume does not seem to add much information to a model that already includes energy consumption and may in fact have a negative correlation with GDP. This suggests that the Li Keqiang index is a flawed measure for the modern economy. While rail cargo volume seems to indicate that more goods are being produced and transported, it also shows that the economy relies on industrial production rather than a strong service or financial industry that produces more value-add.</p>
<p>Additionally, in countries with higher levels of democracy, energy consumption had an even higher effect on GDP than in countries with low levesl of democracy. Since I had expected non-democracies to be overreporting their GDP, I had expected energy consumption to have a lower effect on GDP in countries with higher levels of democracy. As mentioned above, this may suggest that democracies have intrinsically better economies or that they use their resources (such as electricity) for projects that result in stronger development. While percentage of GDP from services and percentage of population in urban areas both had statistically significant interactions with the variables of interest, their effect size was overall very small compared to that of the interactions with levels of democracy. This suggests that they had little impact on the efficacy of the index.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Discussion">Discussion<a class="anchor-link" href="#Discussion">&#182;</a></h1><p>Throughout this project, I have raised some issues with the data and with the models being used.</p>
<h3 id="Data-Issues">Data Issues<a class="anchor-link" href="#Data-Issues">&#182;</a></h3><p>In the end, most of the data used was from Europe alone. This biases the results of the project toward the behavior of Western economies. This is problematic because European economies are generally more developed and ship things shorter distances. The GDP of less developed and larger countries, such as those of Asia and Africa, would <em>a priori</em>, be believed to be better predicted by rail cargo volume. This means that the effect of rail cargo volume may not be detectable, simply because the kinds of economies that rely on it have not been examined adequately. 
Additionally, many of the non-European countries in the analysis had missing values. Consider the following graph from the previous blog post:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">vc</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">'Country'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span> <span class="o">&lt;</span> <span class="mi">12</span>
<span class="n">vc</span> <span class="o">=</span> <span class="n">vc</span><span class="p">[</span><span class="n">vc</span><span class="p">]</span>

<span class="n">dropped_countries</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df</span><span class="p">[</span><span class="s1">'Country'</span><span class="p">]</span><span class="o">.</span><span class="n">isin</span><span class="p">(</span><span class="n">vc</span><span class="o">.</span><span class="n">index</span><span class="p">)][[</span><span class="s1">'Country'</span><span class="p">,</span><span class="s1">'Region'</span><span class="p">]]</span><span class="o">.</span><span class="n">drop_duplicates</span><span class="p">()</span>
<span class="n">dropped_countries</span><span class="p">[</span><span class="s1">'Region'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">countplot</span><span class="p">(</span><span class="n">data</span> <span class="o">=</span> <span class="n">dropped_countries</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">'Region'</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">'Countries with missing values by region'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[14]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Text(0.5, 1.0, &#39;Countries with missing values by region&#39;)</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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DTs7O6NcuXLGjh07DFdXV6N3797m5ZK7G9SqVauMsmXLGnZ2doajo6Px9ttvW/xeGkbyvxMJ/ZTaXZnk6TIZRirfGiIiIiLyBE6fPo2fnx9Dhw7l448/Tu9yXmjTpk2jZ8+e/P777xQpUiRda9m+fTsVK1Zk0aJF5u8OkZeHwoGIiIj8awcOHGDJkiVUqFABFxcXjh07xvjx44mKiuL3339P812LxNL+/fs5ffo0H3zwARUrVkzTxddP0y+//MKOHTt47bXXsLe358CBA4wdOxZXV1cOHjyY6pewyYtH1xyIiIjIv+bo6EhoaChBQUFcv34dV1dXKleuzKhRoxQM/oUGDRpw4cIF3nzzTWbNmvWfb9/FxYX169czefJkbt68SdasWalVqxZjxoxRMHhJ6cyBiIiIiIgAupWpiIiIiIjEUzgQERERERFA4UBEREREROLpgmQRSbO4uDjOnz+Ps7Pzv/p2ThEREfnvGIbBzZs3yZUrV6pfSqhwICJpdv78eTw8PNK7DBEREXkC586dI0+ePCkuo3AgImnm7OwMPPjj4uLiks7ViIiISFpERUXh4eFh/j+eEoUDEUmzhKFELi4uCgciIiIvmLQMCdYFySIiIiIiAigciIiIiIhIPIUDEREREREBdM2BiDyBtz5ZgpWtfXqXIfLU7P1fm/QuQUTkuaAzByIiIiIiAigciIiIiIhIPIUDEREREREBFA5ERERERCSewoGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREUDhQERERERE4ikciIiIiIgIoHAgIiIiIiLxFA5ERERERARQOBARERERkXgKByIiIiIiAigciIiIiIhIPIUDEREREREBFA5eOp6enkyePPk/3+7mzZsxmUxcv379P9+2iIiIiDwdCgfJuHDhAj169CB//vzY2tri4eFB3bp12bhx41PdTuXKlenVq9dTbfN55enpiclkSvQYO3bsU2l/2LBhlCxZ8qm09aQqV66c5D527tw5XesSERERSQvr9C7geRQREUHFihVxc3Nj/PjxFC9enOjoaNatW0e3bt04evTof1qPYRjExsZibf3iv1wjRoygY8eOFtOcnZ3TqZqkRUdHkzFjxidev2PHjowYMcJimoODwxO3Fxsbi8lkIkMGZXkRERF5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ThAREZEXksn4NwPIReS5ERwcTK9evSy+Q+Fpi4qKwtXVlRI9ZmFl+3hnnESeZ3v/1ya9SxAReWYS/n/fuHHD/N1LydGZAxERERERARQOREREREQknsKByEsiMDDwmQ4pEhERkZefwoGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREUDhQERERERE4ikciIiIiIgIoHAgIiIiIiLxFA5ERERERARQOBARERERkXgKByIiIiIiAigciIiIiIhIPIUDEREREREBwDq9CxCRF8+vI5vj4uKS3mWIiIjIU6YzByIiIiIiAigciIiIiIhIPIUDEREREREBFA5ERERERCSewoGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREQCs07sAEXnxnBtbDmc7q/QuQ+SllffTQ+ldgoi8onTmQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREUDhQERERERE4ikciIiIiIgIoHAgIiIiIiLxFA5ERERERARQOBARERERkXgKByIiIiIiAigciIiIiIhIPIUDEREREREBFA5ERERERCSewoGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJ91KGA09PTyZPnpzeZTx1gYGB1K9fP73LeCKVK1emV69ej72eyWRi1apVT72eZ2nz5s2YTCauX78OQHBwMG5ubimuM2zYMEqWLPnMaxMRERFJSbqGg397sJvcQdeePXvo1KnTkxf2kMWLF2NlZUXnzp2fSnv/xpQpUwgODk7vMp6J//rg2DAM5syZQ9myZXFycsLNzQ1/f38mT57MnTt3/lXbFSpUIDIyEldX16dUrYiIiMh/46U8c5AtWzYcHByeSlvz5s2jf//+LF269F8fND6p2NhY4uLicHV1TfUTaEmb1q1b06tXL+rVq0dISAhhYWEMGTKE77//nvXr1z9xu9HR0djY2ODu7o7JZHqKFYuIiIg8e891OJg0aRLFihXD0dERDw8Punbtyq1bt4AHQzfatWvHjRs3MJlMmEwmhg0bBiQeVmQymfjyyy9p0KABDg4OFCxYkNWrV6e6/YiICLZv387AgQPx8/Pju+++s5ifcOZizZo1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aymu06hRI2rWrEmVKlXIli0bS5YsSdO2cuXKxbZt24iNjaVGjRoULVqUDz/8EFdX12QDiclkYvHixUyaNImVK1dSqVIlihcvzrBhw6hXrx41atQAHrwPrl27RqlSpWjdujU9e/ZM8q5RaeHg4MCAAQNo0aIF5cuXx97enqVLl1os4+3tTcOGDQkICOCdd96haNGiFrcq7dChA19++SXBwcEUK1aMSpUqERwcjJeXF/D0Xj8RERF5dZmMZzFIXEReSglDrn4fVAhnu8RnZUTk6cj76aH0LkFEXiIJ/79v3LiR6s1p0v3MgYiIiIiIPB8UDkREREREBFA4EBERERGReAoHIiIiIiICKByIiIiIiEg8hQMREREREQEUDkREREREJJ7CgYiIiIiIAAoHIiIiIiIST+FAREREREQAhQMREREREYmncCAiIiIiIoDCgYiIiIiIxFM4EBERERERQOFARERERETiKRyIiIiIiAigcCAiIiIiIvEUDkREREREBADr9C5ARF48HgN34uLikt5liIiIyFOmMwciIiIiIgIoHIiIiIiISDyFAxERERERARQOREREREQknsKBiIiIiIgACgciIiIiIhJP4UBERERERACFAxERERERiadwICIiIiIigMKBiIiIiIjEUzgQEREREREArNO7ABF58VSfVR1re/35EHlWtvXYlt4liMgrSmcOREREREQEUDgQEREREZF4CgciIiIiIgIoHIiIiIiISDyFAxERERERARQOREREREQknsKBiIiIiIgACgciIiIiIhJP4UBERERERACFAxERERERiadwICIiIiIigMKBiIiIiIjEUzgQERERERFA4UBEREREROIpHIiIiIiICKBwICIiIiIi8RQOREREREQEUDgQEREREZF4CgciIiIiIgIoHEgKIiIiMJlMhIWFpXcpSfL09GTy5MnpXcZTFRwcjJub21Nrr3LlyvTq1euptSciIiIvN4WDV8D27duxsrKiZs2aj7Weh4cHkZGRFC1a9BlV9t/4888/sbGxwc/P76m3vXnzZkwmE9evX3/qbT8NK1as4LPPPkvvMkREROQFoXDwCpg3bx49evTgt99+4+zZs2lez8rKCnd3d6ytrZ9hdc9ecHAwTZo04c6dO2zbti1darh//366bDdz5sw4Ozuny7ZFRETkxaNw8JK7ffs2y5Yto0uX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mJgY+vfvz507d2jRogW5c+dm2rRpvPnmm0+7RhERERER+Q888a1MO3bsyJkzZ7h06RIXLlxg9+7d7N+/H29v76dZn4iIiIiI/EceKxxcv36dli1bki1bNnLlysXUqVPJnDkzX3zxBd7e3uzcuZN58+Y9q1pFREREROQZeqxhRR9//DG//vorbdu2Ze3atfTu3Zu1a9dy9+5dfvrpJypVqvSs6hQRERERkWfsscLBjz/+yPz586lWrRpdu3bF29sbHx8fffGZiIiIiMhL4LGGFZ0/f57ChQsDkD9/fuzs7OjQocMzKUxERERERP5bjxUO4uLiyJgxo/m5lZUVjo6OT70oERERERH57z3WsCLDMAgMDMTW1haAu3fv0rlz50QBYcWKFU+vQhERERER+U88Vjho27atxfNWrVo91WJERERERCT9PFY4mD9//rOq47lXuXJlSpYsmeLF156envTq1YtevXolu4zJZGLlypXUr1+fiIgIvLy82L9/PyVLlnzqNb8sAgMDuX79OqtWrUrvUixs3ryZKlWqcO3aNdzc3J5q20ePHiUwMJCwsDD8/PwICwtLcrng4GB69erF9evXn+r2RURE5NX0xF+C9qILDAzEZDLRuXPnRPO6du2KyWQiMDDQPG3FihV89tln/2GFabN582ZMJlOSjwsXLjyVbXh6ej7Xd6RK6IOiRYsSGxtrMc/NzY3g4OB/vY3KlSunGPqeRKdOnbCysmLp0qWJ5g0dOhRHR0eOHTvGxo0bk22jadOmHD9+/KnWJSIiIq+uVzYcAHh4eLB06VL++ecf87S7d++yZMkS8ubNa7Fs5syZcXZ2/q9LTLNjx44RGRlp8ciePXt6l/WfOnXqFF999dVTbTM6Ovqptpfgzp07fPPNN3z00UcEBQUlmn/q1CneeOMN8uXLR5YsWZKtzd7e/pV7nUVEROTZeaXDQenSpcmbN6/FBdQrVqzAw8ODUqVKWSz76CfHly5dom7dutjb2+Pl5cWiRYsStX/ixAneeust7OzsKFy4ML/88kuqNR05coSAgACcnJzIkSMHrVu35vLly6mulz17dtzd3S0eGTI8eHn37NlD9erVyZo1K66urlSqVIl9+/ZZrD9s2DDy5s2Lra0tuXLlomfPnub9PnPmDL179zafkUjOpEmTKFasGI6Ojnh4eNC1a1du3bplnh8cHIyb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EBERERGReAoHIiIiIiICKByIiIiIiEg8hQMREREREQEUDkREREREJJ7CgYiIiIiIAAoHIiIiIiIST+FAREREREQAhQMREREREYmncCAiIiIiIoDCgYiIiIiIxFM4EBERERERQOFARERERETiWad3ASLy4nlj7c+4uLikdxkiIiLylOnMgYiIiIiIAAoHIiIiIiIST+FAREREREQAhQMREREREYmncCAiIiIiIoDCgYiIiIiIxFM4EBERERERQOFARERERETiKRyIiIiIiAigcCAiIiIiIvEUDkREREREBFA4EBERERGReNbpXYCIvHhmf/wz9rYO6V2GiIjIS6X7xLrpXYLOHIiIiIiIyAMKByIiIiIiAigciIiIiIhIPIUDEREREREBFA5ERERERCSewoGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREUDhQERERERE4ikciIiIiIgIoHAgIiIiIiLxFA5ERERERARQOBARERERkXgKByIiIiIiAigcyL+0efNmTCYT169f/8+3HRERgclkIiws7D/f9rO2bds2ihUrRsaMGalfv36yyw0bNoySJUv+Z3WJiIjIy03h4BV26dIlPvjgA/LmzYutrS3u7u7UqFGDHTt2PPNtx8bGMmbMGPz8/LC3tydz5syUK1eO+fPnP/NtPy/eeecdrKys2LlzZ6J5ffr0oWTJkpw+fZrg4OBk2+jXrx8bN258hlWKiIjIq8Q6vQuQ9NOoUSOio6NZsGAB+fPn5+LFi2zcuJGrV68+820PGzaMOXPmMH36dPz9/YmKiiI0NJRr1649822n5v79+9jY2DzTbZw9e5YdO3bQvXt3goKCKFeunMX8U6dO0blzZ/LkyZPk+oZhEBsbi5OTE05OTs+0VhEREXl16MzBK+r69ev89ttvjBs3jipVqpAvXz7KlCnDoEGDqF27NpD0sJ3r169jMpnYvHmzRXvbtm2jRIkS2NnZUbZsWQ4dOpTi9n/44Qe6du3Ke++9h5eXFyVKlOD999+nT58+5mXWrl3LG2+8gZubG1myZKFOnTqcOnUqUVt//PEHVapUwcHBgRIlSlic+bhy5QrNmzcnT548ODg4UKxYMZYsWWKxfuXKlenevTt9+vQha9asVK9eHYBJkyZRrFgxHB0d8fDw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xgyKFClCnTp1OHHiBPBs9klEREReLiYjpQHSIiIPiYqKwtXVlfHdlmJv65De5YiIiLxUuk+s+0zaTfj/fePGjVSvH9SZAxERERERARQOREREREQknsKBiIiIiIgACgciIiIiIhJP4UBERERERACFAxERERERiadwICIiIiIigMKBiIiIiIjEUzgQERERERFA4UBEREREROIpHIiIiIiICKBwICIiIiIi8RQOREREREQEUDgQEREREZF4CgciIiIiIgIoHIiIiIiISDyFAxERERERARQOREREREQknnV6FyAiL54PRtfCxcUlvcsQERGRp0xnDkREREREBFA4EBERERGReAoHIiIiIiICKByIiIiIiEg8hQMREREREQEUDkREREREJJ7CgYiIiIiIAAoHIiIiIiIST+FAREREREQAhQMREREREYmncCAiIiIiIgBYp3cBIvLi+V/H1thlzJjeZTy3Bn/9XXqXICIi8kR05kBERERERACFAxERERERiadwICIiIiIigMKBiIiIiIjEUzgQERERERFA4UBEREREROIpHIiIiIiICKBwICIiIiIi8RQOREREREQEUDgQEREREZF4CgciIiIiIgIoHIiIiIiISDyFAxERERERARQOREREREQknsKBiIiIiIgACgciIiIiIhJP4UBERERERACFAxERERERiadwICIiIiIigMKBiIiIiIjEUziQZ2LWrFk4OzsTExNjnnbr1i0yZszIm2++abHs1q1bMZlMHD9+/F9tc/PmzZhMJq5fv/6v2vk3hg0bhslkSvTw8/NLt5pERERE0so6vQuQl1OVKlW4desWoaGhlCtXDngQAtzd3dmzZw937tzBwcEBeHBQnytXLnx8fNKzZDPDMIiNjcXa+sl+PYoUKcKGDRsspj1pWwmio6PJmDHjv2pDREREJDU6cyDPhK+vL7ly5WLz5s3maZs3b6ZevXoUKFCA7du3W0yvUqUKAPfv36d///7kzp0bR0dHypYta9HGmTNnqFu3LpkyZcLR0ZEiRYrw008/ERERYW4jU6ZMmEwmAgMDgQcH++PHjyd//vzY29tTokQJvvvuO4vtm0wm1q1bh7+/P7a2tmzdupXKlSvTs2dP+vfvT+bMmXF3d2fYsGGp7ru1tTXu7u4Wj6xZs5rnm0wmVq1aZbGOm5sbwcHBAERERGAymVi2bBmV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s8lkwt3dnUuXLj154SLyXFI4EBEReYHZ29snO88wDEwmU5LzEqZnyJABwzAs5kVHRydaPmPGjInWj4uLe9xyReQ5p3AgIiLyAitYsCD29vZs3Lgx0bzChQsTFhbG7du3zdO2bdtGhgwZ8PHxASBbtmxERkaa58fGxvL7778/Vg02NjbmdUXkxaZwICIi8gKzs7NjwIAB9O/fn6+++opTp06xc+dOgoKCaNmyJXZ2drRt25bff/+dkJAQevToQevWrc3XG1StWpUff/yRH3/8kaNHj9K1a1euX7/+WDVkz54de3t71q5dy8WLF7lx48Yz2FMR+S8oHIiIiLzghgwZQt++ffn0008pVKgQTZs25dKlSzg4OLBu3TquXr3K66+/TuPGjXn77beZPn26ed327dvTtm1b2rRpQ6VKlfDy8qJKlSqPtX1ra2umTp3K7NmzyZUrF/Xq1Xvauygi/xGT8ehAQxEREREReSXpzIGIiIiIiAAKByIiIiIiEk/hQEREREREAIUDERERERGJp3AgIiIiIiKAwoGIiIiIiMRTOBAREREREUDhQERERERE4ikciIiIiIgIoHAgIiIiIiLxFA5ERERERARQOBARERERkXj/B+owO9EJGiKDAAAAAElFTkSuQmCC"
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Non-European countries, especially in Africa, were the countries which were most likely to have some data missing. This means that the countries whose economies were <em>a priori</em> believed to be best represented by measures of rail cargo volume were also the most likely to be themselves inadequately represented. This is especially problematic when you look at countries that have fewer than four data points:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[15]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">vc</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">'Country'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span> <span class="o">&lt;</span> <span class="mi">4</span>
<span class="n">vc</span> <span class="o">=</span> <span class="n">vc</span><span class="p">[</span><span class="n">vc</span><span class="p">]</span>

<span class="n">dropped_countries</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df</span><span class="p">[</span><span class="s1">'Country'</span><span class="p">]</span><span class="o">.</span><span class="n">isin</span><span class="p">(</span><span class="n">vc</span><span class="o">.</span><span class="n">index</span><span class="p">)][[</span><span class="s1">'Country'</span><span class="p">,</span><span class="s1">'Region'</span><span class="p">]]</span><span class="o">.</span><span class="n">drop_duplicates</span><span class="p">()</span>
<span class="n">dropped_countries</span><span class="p">[</span><span class="s1">'Region'</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">countplot</span><span class="p">(</span><span class="n">data</span> <span class="o">=</span> <span class="n">dropped_countries</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">'Region'</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">'Countries with less than four values by region'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[15]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Text(0.5, 1.0, &#39;Countries with less than four values by region&#39;)</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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nKKiovTKK68k+hrt0qWL7OzstGjRIo0fP15btmyxvPFPrtb//Oc/kqR58+Zp586dGjJkiCRpzJgx6ty5s4oUKaIVK1Zo8uTJOnjwoMqXL68//vgjhaOQtNS+vjt27Kiff/45wbrWrVunc+fOqWPHjpZpp06d0jvvvKNly5ZpxYoVaty4sd59912NGDEizXU+bvPmzapYsaKuX7+umTNn6ttvv1XJkiXVokULqxDRr18/zZgxQ71799batWu1YMECNWvWzPK6Sknnzp2VKVMmy9C0PXv2qHLlypbf13feeUe2traaNWuW1XJXr17VkiVL1LlzZzk6Oia7jvv37+utt95S1apV9e2332r48OGKi4tTgwYNNHbsWLVu3Vrff/+9xo4dq/Xr16ty5cr6+++/Lct37NhRoaGh6tixo7799ls1adJEjRo1StW1KosWLVKDBg3k7u6uxYsXKywsTNeuXVPlypX1888/J2jfpEkTFSxYUMuXL9eHH36oRYsWqW/fvinvyJeJAQCwcv78eUOS0bJly1S1j4yMNCQZPXr0sJq+e/duQ5Lx0UcfWablyZPH6NChQ4I+KlWqZFSqVMnyfPPmzYYko06dOlbtli1bZkgydu7caZlWt25dI0+ePAn6PHnypCHJyJ8/v3H//v1E582bN88yrVatWkbu3LmNGzduWLXt1auX4ejoaFy9etUwDMOoV6+eUbJkyUT3RXK++OILQ5Jx5swZwzAMY+TIkUZQUJDx1ltvGR07djQMwzDu379vuLi4WO2zoUOHGo//uypSpIjV/or3JPstMfPmzTMkGSdPnjQMwzCio6MNLy8vo379+lbtYmNjjRIlShhly5a1THN1dTX69OmTZN/79u0zJBmrVq1KtobEpHSMixUrZsTExFim79mzx5BkLF68OMk+Y2JijNu3bxsuLi7G5MmTLdPj98Hjr+fx48cbkoyoqKhka41ffu/evZZp165dM5ycnBIclzNnzhgODg5G69atLdMe/12I16FDB6t9kNzrOzGXL1827O3trV5bhmEYzZs3N7Jnz248ePAg0eViY2ONBw8eGJ988omRJUsWIy4uLsla419/mzdvtuojsd+3oKAgo1SpUgnWW69ePSNHjhxGbGysYRiGUbRoUaNhw4Ypbt/j4o9Do0aNrKZv377dkGSMHDnSMq1Dhw5GtmzZjHv37lmm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"
class="
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Africa and the Middle East are extremely overrepresented among these countries, and in fact most of the African and Middle Eastern countries with missing values have fewer than four total values. Because three is the minimum number of data points needed to create a linear regression, this suggests that the data simply does not exist to make an adequate conclusion based on these countries. Meanwhile, Europe and North America are represented strongly in the data and have the most influence on the data results show. This has data ethics implications: is it really ethical to make conclusions about economic indicators like the Li Keqiang Index based on data that prioritizes wealthy, Western economies? It's possible that the woefully inadequate data being gathered on the Global South is leading to misconceptions about those economies.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Model-Issues">Model Issues<a class="anchor-link" href="#Model-Issues">&#182;</a></h3><p>As I mentioned above, the <code>mixedlm()</code> function in the <code>statsmodels</code> package for Python doesn't appear to have any way to deal with heteroskedasticity, despite this presumably being a relatively common problem for statisticians using mixed linear models to face. This means that the standard errors of this analysis, thus decisions about whether a particular variable in a model is statistically significant or not, are skewed. Additionally, one glaring omission from this model is the third element of the Li Keqiang index: bank loan volume. As far as I could tell, there is no public data on this for any country in the world, and it would be extremely difficult to get it in most countries. Li Keqiang could do so because he had developed his economic indicators while he was the effective governor of his province in a country where the banks are directly controlled by the government. Most other researchers, however, do not have such a luxury.</p>
<p>All of this, combined with the data issues above, limits the usability of the mixed linear model for evaluating the Li Keqiang index.</p>

</div>
</div>
</div>
</div>
</body>







</html>
