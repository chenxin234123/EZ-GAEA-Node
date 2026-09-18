# How EZ Gaea Node was made

[简体中文](DESIGN.zh-CN.md) · [Project overview](README.md)

## The problem

Gaea's node names and reference material are primarily in English. Looking up unfamiliar terms while building terrain interrupts the creative process. EZ Gaea Node puts reference material beside Gaea and lets the reader choose the languages they understand.

## The central idea

The application combines a local reference library with a node-identification layer:

**Search or click in Gaea → identify the node → find its local document → display the selected languages.**

Reading a document does not generate a fresh AI answer. The translations are prepared in advance, so ordinary lookup works offline and does not require an AI account or API key.

## Preparing the reference library

The documentation was collected from the [official node reference](https://docs.gaea.app/reference), organized into node introductions, parameter groups, parameters, option descriptions, usage guidance and visual references, and saved as local data. The [official Macro documentation](https://docs.gaea.app/developers/extensibility/macros/) is also included. Original English identifiers and source links are retained so a translated title can still be traced back to the corresponding node.

If a source page has a parameter name but no explanation, the name is retained without inventing a description. The bundled library is a snapshot of 183 nodes, not a guarantee that every future Gaea node or documentation update is already included.

## Following a selection

On Windows, the helper observes mouse-release and foreground-window events. It checks whether the target is the expected Gaea application, then uses Windows UI Automation to read text exposed by the property panel, such as the node-type heading, groups, parameter names and help text. It does not use screenshot OCR for this identification path.

Those signals are compared with the local catalog. Explicit aliases bridge known naming differences; for example, the observed name FlowClassic can resolve to the documented FlowMapClassic entry while keeping the documentation name intact. Some nodes expose few parameters, so targeted rules additionally check the selection count and stable node-type captions.

An ambiguous or unavailable result is shown as such. The current document is retained and users can select a suggested document or search manually. The design focuses on inspecting one node at a time.

## Keeping the interface responsive

Closely spaced clicks are briefly coalesced. Property-panel reads run in a separate helper process instead of blocking the main interface. Cached panel information reduces repeated work. Timeouts and a check for newer selections prevent an old response from replacing a more recent result. Repeated timeouts pause following while manual search remains available. This design reduces risk; it is not a guarantee that every Gaea version exposes identical UI information.

## Languages and reading

Node identity is kept separate from displayed text. English node and parameter names remain visible, with translated names beside them. Readers can select one or several languages, and descriptions are displayed in that order. Search also understands localized node names.

English comes from the reference library. Existing Simplified Chinese translations are retained; Traditional Chinese is derived from them. Japanese, German, Spanish, French and Korean were directly retranslated with GPT-6, with 2,926 unique text entries per language across documentation and UI. Coverage checks, terminology corrections, numeric and condition checks, and contextual sampling were performed. This is not a claim of professional native-speaker review.

## Local data and application boundaries

This is a standalone Windows companion built with C# and WPF for .NET Framework 4.8. It does not install a component inside Gaea or generate terrain itself. In its normal following path it reads exposed interface information; it does not edit node parameters. Settings and the most recent recognition diagnostic are stored locally in UserData. Official-document and author links open the browser when clicked.

The current target check expects Gaea.exe in a path containing \Gaea 2\. Compatibility with every later Gaea release is not guaranteed; manual document search remains independent of Gaea.

## What is shared here

This repository shares the compiled application, user documentation and this design explanation. It does not publish the application's implementation source code or build project. JSON files in the download are runtime reference and language data. The upstream Gaea2-Docs material retains its MIT notice; that notice does not label the entire companion application as MIT licensed.

Author: [chenxin234123](https://www.artstation.com/chenxin234123).

## Manual update link

The ellipsis menu contains a localized Check for update entry. Clicking it opens https://github.com/chenxin234123/EZ-GAEA-Node in the default browser. The application contains no update-checking, package-download or automatic-installation service.
