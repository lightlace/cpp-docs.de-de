---
title: "MSBuild Error MSB1003"
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
  - "MSBuild.MissingProjectError"
helpviewer_keywords: 
  - "MSB1003"
ms.assetid: db4aa779-af86-4bb6-b86f-9a31866f70f5
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1003
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="a21f07e105ae1c706a3a4805af49e925" class="tgtSentence">Geben Sie eine Projekt- oder Projektmappendatei an.\</caps:sentence>
        \<caps:sentence id="tgt2" sentenceid="f671eae5d94b7e5e007763fd5220ef96" class="tgtSentence">Das aktuelle Arbeitsverzeichnis enthält keine Projekt- oder Projektmappendatei.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt3" sentenceid="7235e2e4995d3fcf66fc8c75ee1b73c1" class="tgtSentence">Wenn an der Befehlszeile keine Projekt- oder Projektmappendatei angegeben wird, durchsucht <token>vstecmsbuild</token> das aktuelle Arbeitsverzeichnis nach einer Datei mit der Dateierweiterung "proj" oder "sln" und verwendet diese Datei.\</caps:sentence>  \<caps:sentence id="tgt4" sentenceid="632f83de4e27a3b5015b21f48c09a999" class="tgtSentence">Das aktuelle Arbeitsverzeichnis enthält keine Datei, deren Dateierweiterung auf "proj" oder "sln" endet.\</caps:sentence>  </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="tgt5" sentenceid="4d62a4cb805c10fb18463bc7c32e055f" class="tgtSentence">So beheben Sie diesen Fehler\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt6" sentenceid="72251b54c4a3962f81c8f9e8cdbb1ec9" class="tgtSentence">Wechseln Sie zum Verzeichnis mit der zu erstellenden Projektdatei.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt7" sentenceid="e0d7ea6d56bd3cc901ce8af60e0f4bb6" class="tgtSentence">Geben Sie den vollständigen oder relativen Pfad zur Projektdatei an.\</caps:sentence>  \<caps:sentence id="tgt8" sentenceid="4a7c757d5b6745fb14b78ee59dd0bb85" class="tgtSentence">Geben Sie beispielsweise <codeInline>msbuild c:\myapp\myapp.proj</codeInline> oder <codeInline>msbuild ..\..\myapp\myapp.proj</codeInline> ein.\</caps:sentence>  </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt9" sentenceid="ae41a0eacfaf6862382f2fbefeab9e3c" class="tgtSentence">Wenn die Projekt- oder Projektmappendatei über eine Dateierweiterung verfügt, die nicht auf "proj" endet, ändern Sie die Dateierweiterung entsprechend.\</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="d9a68146-1f43-4621-ac78-2c8c3f400936">MSBuild Project File Schema Reference</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">Specify a project or solution file.\</caps:sentence>  \<caps:sentence id="src2" class="srcSentence">The current working directory does not contain a project or solution file.\</caps:sentence>  </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src3" class="srcSentence">If a project or solution file is not specified on the command line, <token>vstecmsbuild</token> searches the current working directory for a file that has a file extension that ends in "proj" or "sln" and uses that file.\</caps:sentence>  \<caps:sentence id="src4" class="srcSentence">The current working directory does not contain a file that has a file extension that ends in "proj" or "sln".\</caps:sentence>  </para>
      </introduction>
      <procedure>
        <title>
          \<caps:sentence id="src5" class="srcSentence">To correct this error\</caps:sentence>
        </title>
        <steps class="bullet">
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src6" class="srcSentence">Go to the directory that contains the project file you want to build.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src7" class="srcSentence">Specify either the full or relative path to the project file.\</caps:sentence>  \<caps:sentence id="src8" class="srcSentence">For example, type <codeInline>msbuild c:\myapp\myapp.proj</codeInline> or <codeInline>msbuild ..\..\myapp\myapp.proj</codeInline>\</caps:sentence>  </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src9" class="srcSentence">If the project or solution file has a file extension that does not end in "proj", change the file extension so that it does end in "proj".\</caps:sentence>
          </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="edaa65ec-ab8a-42a1-84cb-d76d5b2f4584">MSBuild Command Line Reference</link>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="d9a68146-1f43-4621-ac78-2c8c3f400936">MSBuild Project File Schema Reference</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>