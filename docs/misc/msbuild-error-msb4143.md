---
title: "MSBuild-Fehler MSB4143"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4143"
ms.assetid: 25019aa4-f0da-4bcd-862e-9b5a57913bb4
caps.latest.revision: 10
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild-Fehler MSB4143
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="e02778ffc878a05fdb6079933e67e6f1" class="tgtSentence">MSB4143: Der Ausdruck "&lt;Ausdruck&gt;" kann nicht ausgewertet werden.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="7bd2947eec96d0fc34b9afe902b07c74" class="tgtSentence">Ein Eigenschaftsausdruck, der seinen Wert aus der Registrierung abruft, kann nicht ausgewertet werden.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="tgt3" sentenceid="4d62a4cb805c10fb18463bc7c32e055f" class="tgtSentence">So beheben Sie diesen Fehler\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt4" sentenceid="ada6f70249dc9a4f73be24a19f8600a7" class="tgtSentence">Stellen Sie sicher, dass die Eigenschaft die richtige Syntax zum Abrufen eines Werts aus der Registrierung verwendet.\</caps:sentence>  \<caps:sentence id="tgt5" sentenceid="1402ae63c8033d1007e6ef4cd492651a" class="tgtSentence">Beispiel: <codeInline>$(Registry:HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\MSBuild@MSBuildBinPath)</codeInline>.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
        \<link xlink:href="d1cda56a-dbef-4109-9201-39e962e3f653">Project Element (MSBuild)</link>
        \<link xlink:href="29dd85ee-1530-43c1-b085-bb2330ac5a48">Resources for Troubleshooting MSBuild Errors</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">MSB4143: The expression "&lt;expression&gt;" cannot be evaluated.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">A property expression that reads its value from the registry cannot be evaluated.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="src3" class="srcSentence">To correct this error\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src4" class="srcSentence">Make sure that the property follows the correct syntax to read a value from the registry.\</caps:sentence>  \<caps:sentence id="src5" class="srcSentence">For example: <codeInline>$(Registry:HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\MSBuild@MSBuildBinPath)</codeInline>.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
        \<link xlink:href="d1cda56a-dbef-4109-9201-39e962e3f653">Project Element (MSBuild)</link>
        \<link xlink:href="29dd85ee-1530-43c1-b085-bb2330ac5a48">Resources for Troubleshooting MSBuild Errors</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>