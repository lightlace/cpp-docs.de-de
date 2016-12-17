---
title: "MSBuild Error MSB1005"
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
  - "MSBuild.MissingPropertyError"
helpviewer_keywords: 
  - "MSB1005"
ms.assetid: cf4e8503-46fb-4c1e-a1ca-aa344276ebb0
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1005
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="fd0d81389cdb9fdbbbade4df94517bbb" class="tgtSentence">Geben Sie eine Eigenschaft und ihren Wert an.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="8fe4e1a851d88586ac6a271058486f8c" class="tgtSentence">Eigenschaftenname und -wert müssen für den Schalter <system>/property</system> angegeben werden.\</caps:sentence>
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
            \<caps:sentence id="tgt4" sentenceid="44c1203d927d0791728d4ccbe41633f8" class="tgtSentence">Geben Sie einen Eigenschaftennamen und -wert im Format <codeInline>/property:&lt;name&gt;=&lt;value&gt;</codeInline> an.\</caps:sentence>  \<caps:sentence id="tgt5" sentenceid="6ed7d2222bf90edd287b27797807f21b" class="tgtSentence">Sie können entweder ein Komma oder ein Semikolon verwenden, um Eigenschaften in einer Liste zu trennen, z. B. <codeInline>/property:WarningLevel=2;OutputDir=bin\Debug</codeInline> oder <codeInline>/property:WarningLevel=2,OutputDir=bin\Debug</codeInline>.\</caps:sentence>  \<caps:sentence id="tgt6" sentenceid="2c5e1978cfacb3782a47e8bb2f8d5c2f" class="tgtSentence">Alternativ können Sie den Schalter wiederholen, z. B. <codeInline>/p:WarningLevel=2 /p:OutputDir=bin\Debug</codeInline>.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">Specify a property and its value.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">A property name and value must be specified for the <system>/property</system> switch.\</caps:sentence>
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
            \<caps:sentence id="src4" class="srcSentence">Specify a property name and value using the format <codeInline>/property:&lt;name&gt;=&lt;value&gt;</codeInline>.\</caps:sentence>  \<caps:sentence id="src5" class="srcSentence">You can use either a comma or a semicolon to separate a list of properties, for example, <codeInline>/property:WarningLevel=2;OutputDir=bin\Debug</codeInline> or <codeInline>/property:WarningLevel=2,OutputDir=bin\Debug</codeInline>.\</caps:sentence>  \<caps:sentence id="src6" class="srcSentence">Alternatively, you can repeat the switch, for example, <codeInline>/p:WarningLevel=2 /p:OutputDir=bin\Debug</codeInline>\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="962912ac-8931-49bf-a88c-0200b6e37362">MSBuild Properties</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>