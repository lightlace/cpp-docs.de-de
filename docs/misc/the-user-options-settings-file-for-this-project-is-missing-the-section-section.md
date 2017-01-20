---
title: "The user options settings file for this project is missing the &#39;section&#39; section"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.peruserfile_sectionerr"
ms.assetid: 576070f5-76b6-46e4-8aba-83442521027f
caps.latest.revision: 7
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# The user options settings file for this project is missing the &#39;section&#39; section
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt1" sentenceid="a8b2eb2af9c399d233cbcc2c5f69e49b" class="tgtSentence">In der <legacyBold>.vbproj.user</legacyBold>-Datei oder der <legacyBold>.csproj.user</legacyBold>-Datei fehlt der <UI>Build</UI>-Knoten.\</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="2e44faebe867e00cbdfa07a108d11a35" class="tgtSentence">Der <UI>Build</UI>-Abschnitt enthält Debugeinstellungen.\</caps:sentence>  \<caps:sentence id="tgt3" sentenceid="890e7db1f65cede6a4986230e2bfd789" class="tgtSentence">Wenn dieser Abschnitt fehlt, werden die Debugeinstellungen nicht geladen, und die Standardwerte werden verwendet.\</caps:sentence>  </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt4" sentenceid="1d63d83e21d5b59ec624f5806b977de4" class="tgtSentence">Dieser Fehler wird meistens durch das manuelle Bearbeiten der Projektdatei verursacht. \</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt5" sentenceid="8aaa5f49f2d0d8ffc4222f3475e89f2a" class="tgtSentence">Das Projektsystem schreibt die benutzerbezogene Projektdatei automatisch neu, wenn das Projekt geschlossen wird.\</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt6" sentenceid="704e05301dbfc2267ab3ca77cab8c778" class="tgtSentence">Diese Warnung ist als Information zu verstehen.\</caps:sentence>
    </para>
      </introduction>
      <relatedTopics>
        \<link xlink:href="5261CF45-3136-40A6-899E-DC1339551401">Format of a .vcproj File</link>
        \<legacyLink xlink:href="EB4C97ED-F667-4850-98D0-6E2A4D21BBCA">NIB: Project Properties (Visual Studio)</legacyLink>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="src1" class="srcSentence">The Build node is missing from the.vbproj.user or .csproj.user file.\</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">The Build section encompasses debugging settings.\</caps:sentence>  \<caps:sentence id="src3" class="srcSentence">If this section is missing, your debugging settings will not be loaded and will take on default values.\</caps:sentence>  </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src4" class="srcSentence">The situation is most likely caused by editing the project file by hand. \</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src5" class="srcSentence">The project system will automatically rewrite the per-user project file when the project is closed.\</caps:sentence>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src6" class="srcSentence">This is an informational warning.\</caps:sentence>
    </para>
      </introduction>
      <relatedTopics>
        \<link xlink:href="5261CF45-3136-40A6-899E-DC1339551401">Format of a .vcproj File</link>
        \<legacyLink xlink:href="EB4C97ED-F667-4850-98D0-6E2A4D21BBCA">NIB: Project Properties (Visual Studio)</legacyLink>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>