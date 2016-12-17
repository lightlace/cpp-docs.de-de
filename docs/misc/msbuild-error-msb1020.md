---
title: "MSBuild Error MSB1020"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.LoggerNotFoundError"
helpviewer_keywords: 
  - "MSB1020"
ms.assetid: 75fcb139-0c45-4bf1-a176-60bfb9d1baa4
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1020
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="1eb00946c8782dd5fde2474fdb7da28d" class="tgtSentence">Die Protokollierung konnte nicht gefunden werden.\</caps:sentence>
        \<caps:sentence id="tgt2" sentenceid="931a125c171f6e8415f183e70c7d6e8b" class="tgtSentence">Überprüfen Sie folgende Punkte: 1.) Der angegebene Protokollierungsname stimmt mit dem Namen der Protokollierungsklasse überein.\</caps:sentence>
        \<caps:sentence id="tgt3" sentenceid="61540de1a6a12b3732b2a674f58e2d55" class="tgtSentence">2.) Die Protokollierungsklasse ist "public" und implementiert die Microsoft.Build.Framework.ILogger-Schnittstelle.\</caps:sentence>
        \<caps:sentence id="tgt4" sentenceid="935ca58a23030c1a8f5f8cf69195000e" class="tgtSentence">3.) Der Pfad der Protokollierungsassembly ist richtig, oder die Protokollierung kann nur mit dem angegebenen Assemblynamen geladen werden.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt5" sentenceid="9172f678567db571149d619af78e28d0" class="tgtSentence">Die angegebene Protokollierung wurde nicht gefunden.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="tgt6" sentenceid="4d62a4cb805c10fb18463bc7c32e055f" class="tgtSentence">So beheben Sie diesen Fehler\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt7" sentenceid="b2966d83213d97008bb8158f4fbdc427" class="tgtSentence">Vergewissern Sie sich, dass der angegebene Protokollierungsname mit dem Namen der Protokollierungsklasse übereinstimmt.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt8" sentenceid="c2981403ef5942b5311e2e4651ec0e83" class="tgtSentence">Vergewissern Sie sich, dass die Protokollierungsklasse "public" ist und die <codeEntityReference autoUpgrade="true">T:Microsoft.Build.Framework.ILogger</codeEntityReference>-Schnittstelle implementiert.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt9" sentenceid="eb6747cf256031ed37487ff30f5eb93f" class="tgtSentence">Vergewissern Sie sich, dass der Pfad der Protokollierungsassembly ist richtig und die Protokollierung nur mit dem angegebenen Assemblynamen geladen werden kann.\</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="fa34810d-185a-4d22-92bd-9852915e5f1d">How To: Write a Logger</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">The logger was not found.\</caps:sentence>  \<caps:sentence id="src2" class="srcSentence">Check the following: 1.) The logger name specified is the same as the name of the logger class.\</caps:sentence>  \<caps:sentence id="src3" class="srcSentence">2.) The logger class is "public" and implements the Microsoft.Build.Framework.ILogger interface.\</caps:sentence>  \<caps:sentence id="src4" class="srcSentence">3.) The path to the logger assembly is correct, or the logger can be loaded using only the assembly name provided.\</caps:sentence>  </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src5" class="srcSentence">The specified logger was not found.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="src6" class="srcSentence">To correct this error\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src7" class="srcSentence">Check that the logger name specified is the same as the name of the logger class.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src8" class="srcSentence">Check that the logger class is public and implements the <codeEntityReference autoUpgrade="true">T:Microsoft.Build.Framework.ILogger</codeEntityReference> interface.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src9" class="srcSentence">Check that the path to the logger assembly is correct, or the logger can be loaded using only the assembly name provided.\</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="fa34810d-185a-4d22-92bd-9852915e5f1d">How To: Write a Logger</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>