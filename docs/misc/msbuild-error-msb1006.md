---
title: "MSBuild Error MSB1006"
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
  - "MSBuild.InvalidPropertyError"
helpviewer_keywords: 
  - "MSB1006"
ms.assetid: 6d97d164-66f1-47bf-9cd9-7422a6c0dbb3
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1006
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="e4961729de67aee43e912af53a98b452" class="tgtSentence">Die Eigenschaft ist ungültig.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="660d115df3fc635b36f996117225654f" class="tgtSentence">Der Eigenschaftenname oder der Eigenschaftswert wurde nicht angegeben, z. B. <codeInline>/property:=Debug</codeInline> oder <codeInline>/property:Configuration</codeInline>.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="tgt3" sentenceid="4d62a4cb805c10fb18463bc7c32e055f" class="tgtSentence">So beheben Sie diesen Fehler\</caps:sentence>
        </title>
        <steps class="ordered">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt4" sentenceid="0513311bdd716739f40182974f3adbc6" class="tgtSentence">Geben Sie sowohl den Eigenschaftennamen als auch den Eigenschaftswert an, z. B. <codeInline>/property:Configuration=Debug</codeInline>. \</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">Property is not valid.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">The property name or the property value is not specified, for example, <codeInline>/property:=Debug</codeInline> or <codeInline>/property:Configuration</codeInline>.\</caps:sentence>
    </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="src3" class="srcSentence">To correct this error\</caps:sentence>
        </title>
        <steps class="ordered">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src4" class="srcSentence">Specify both the property name and the property value, for example, <codeInline>/property:Configuration=Debug</codeInline>. \</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>