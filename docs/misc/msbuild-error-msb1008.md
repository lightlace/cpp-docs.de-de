---
title: "MSBuild Error MSB1008"
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
  - "MSBuild.DuplicateProjectSwitchError"
helpviewer_keywords: 
  - "MSB1008"
ms.assetid: 16012f0d-b2d7-424c-9fa0-067e4df1b3e7
caps.latest.revision: 13
caps.handback.revision: "10"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1008
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="bf9d518295606c7758b563235582a730" class="tgtSentence">Es darf nur ein Projekt angegeben werden.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="73a69c5aa4668884e1b46e2999253c60" class="tgtSentence">
        <token>vstecmsbuild</token> kann nur ein Projekt erstellen.\</caps:sentence>
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
            \<caps:sentence id="tgt4" sentenceid="56261debbc2f78a1982a958bf65f8ef2" class="tgtSentence">Geben Sie nur ein zu erstellendes Projekt an.\</caps:sentence>  \<caps:sentence id="tgt5" sentenceid="1ebfffef1c051f5a64b0622b9b0c1af9" class="tgtSentence">Wenn Sie zwei Projekte erstellen möchten, erstellen Sie erst das eine und dann das andere Projekt.\</caps:sentence>  \<caps:sentence id="tgt6" sentenceid="61241e0d0da637870819f692acd1e65b" class="tgtSentence">Anstatt <codeInline>msbuild myapp1.proj myapp2.proj</codeInline> einzugeben, erstellen Sie beispielsweise das erste Projekt durch Eingabe von <codeInline>msbuild myapp1.proj</codeInline> und nach Fertigstellung dieses Builds das zweite Projekt, indem Sie <codeInline>msbuild myapp2.proj</codeInline> eingeben.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="76577f6c-7669-44ad-a840-363e37a04d34">MSBuild Task</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">Only one project can be specified.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">
        <token>vstecmsbuild</token> can build only one project.\</caps:sentence>
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
            \<caps:sentence id="src4" class="srcSentence">Specify only one project to build.\</caps:sentence>  \<caps:sentence id="src5" class="srcSentence">If you want to build two projects, build one project then build the other project.\</caps:sentence>  \<caps:sentence id="src6" class="srcSentence">For example, instead of typing <codeInline>msbuild myapp1.proj myapp2.proj</codeInline>, build the first project by typing <codeInline>msbuild myapp1.proj</codeInline>, and then, when that build is complete, build the second project by typing <codeInline>msbuild myapp2.proj</codeInline>.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="76577f6c-7669-44ad-a840-363e37a04d34">MSBuild Task</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>