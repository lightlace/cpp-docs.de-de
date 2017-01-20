---
title: "The project file is missing the &#39;section&#39; section"
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
  - "vs.tasklisterror.projfile_sectionerr"
ms.assetid: 516ab410-1b73-4539-9654-6323af6135b2
caps.latest.revision: 7
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# The project file is missing the &#39;section&#39; section
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt1" sentenceid="fa4408076bea26283810f2a51b2109e4" class="tgtSentence">Die VBPROJ-Datei oder die CSPROJ-Datei ist beschädigt.\</caps:sentence>  \<caps:sentence id="tgt2" sentenceid="979d41737df3f5c506168c1ad26cb0f1" class="tgtSentence">Einer der folgenden Abschnitte fehlt:\</caps:sentence>  </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt3" sentenceid="13e8775d0a0d4c08cd0ce1210b368c2c" class="tgtSentence">Build \</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt4" sentenceid="45b963397aa40d4a0063e0d85e4fe7a1" class="tgtSentence">Dateien\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt5" sentenceid="deb2933f351254aecac6efd85770abde" class="tgtSentence">VisualStudio\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt6" sentenceid="5ec729d1b0282f39462dd4cf293f5f39" class="tgtSentence">
            <legacyBold>VisualBasic</legacyBold> oder <legacyBold>CSHARP</legacyBold>\</caps:sentence>
        </para>
          </listItem>
        </list>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt7" sentenceid="e9d023d4f8afef67513435cfb039f853" class="tgtSentence">Wenn die Abschnitte <legacyBold>VisualStudio</legacyBold>, <legacyBold>VisualBasic</legacyBold> oder <legacyBold>CSHARP</legacyBold> fehlen, wird das Projekt nicht geladen.\</caps:sentence>  \<caps:sentence id="tgt8" sentenceid="5be75ba8474521be2f96a066e036e66c" class="tgtSentence">Wenn der Abschnitt <UI>Build</UI> oder <legacyBold>Files</legacyBold> fehlt, wird die Projektdatei wie folgt geladen:\</caps:sentence>  </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt9" sentenceid="95de7988564bb1f17538c011625b738c" class="tgtSentence">Wenn <UI>Build</UI> fehlt, gehen alle Buildeinstellungen und Konfigurationsinformationen verloren.\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt10" sentenceid="1cc3092b077325c6faab105015802d24" class="tgtSentence">Wenn <legacyBold>Files</legacyBold> fehlt, enthält das Projekt keine Dateien.\</caps:sentence>
        </para>
          </listItem>
        </list>
        \<para xml:space="preserve">
      <embeddedLabel>
        \<caps:sentence id="tgt11" sentenceid="4d62a4cb805c10fb18463bc7c32e055f" class="tgtSentence">So beheben Sie diesen Fehler\</caps:sentence>
      </embeddedLabel>
    </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="tgt12" sentenceid="8e61bcca96dda6cb44ad4d19ecc89d75" class="tgtSentence">Erstellen Sie das Projekt neu.\</caps:sentence>
        </para>
          </listItem>
        </list>
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
      \<caps:sentence id="src1" class="srcSentence">The .vbproj or .csproj file is corrupt.\</caps:sentence>  \<caps:sentence id="src2" class="srcSentence">One of the following sections is missing:\</caps:sentence>  </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src3" class="srcSentence">Build \</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src4" class="srcSentence">Files\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src5" class="srcSentence">VisualStudio\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src6" class="srcSentence">VisualBasic or CSHARP\</caps:sentence>
        </para>
          </listItem>
        </list>
        \<para xml:space="preserve">
      \<caps:sentence id="src7" class="srcSentence">If the VisualStudio, VisualBasic, or CSHARP section is missing, the project will not load.\</caps:sentence>  \<caps:sentence id="src8" class="srcSentence">If the Build or Files section is missing, the project file will load as follows:\</caps:sentence>  </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src9" class="srcSentence">If Build is missing, all build settings and configuration information will be lost.\</caps:sentence>
        </para>
          </listItem>
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src10" class="srcSentence">If Files is missing, the project will have no files in it.\</caps:sentence>
        </para>
          </listItem>
        </list>
        \<para xml:space="preserve">
      <embeddedLabel>
        \<caps:sentence id="src11" class="srcSentence">To correct this error\</caps:sentence>
      </embeddedLabel>
    </para>
        <list class="bullet">
          <listItem>
            \<para xml:space="preserve">
          \<caps:sentence id="src12" class="srcSentence">Recreate your project.\</caps:sentence>
        </para>
          </listItem>
        </list>
      </introduction>
      <relatedTopics>
        \<link xlink:href="5261CF45-3136-40A6-899E-DC1339551401">Format of a .vcproj File</link>
        \<legacyLink xlink:href="EB4C97ED-F667-4850-98D0-6E2A4D21BBCA">NIB: Project Properties (Visual Studio)</legacyLink>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>