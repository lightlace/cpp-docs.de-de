---
title: "MSBuild Error MSB2003"
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
  - "MSBuild.ProjectFileNotFound"
helpviewer_keywords: 
  - "MSB2003"
ms.assetid: 2686117d-acc6-4222-93cd-2354cd3e1134
caps.latest.revision: 14
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB2003
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="tgt1" sentenceid="a5d633ac064a0ec39e99e12cbb65e226" class="tgtSentence">Der Dateiname des alten Projekts muss angegeben werden.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt2" sentenceid="e848fb78e2387c8128735579e583a164" class="tgtSentence">Diese Projektdatei ist am erwarteten Speicherort nicht vorhanden.\</caps:sentence>
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
            \<caps:sentence id="tgt4" sentenceid="895fcf3f75f98442d15ec041d7e03f6c" class="tgtSentence">Überprüfen Sie, ob die Projektdatei verschoben wurde.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt5" sentenceid="7ec3692dccdbdab027c095a788fc0d1b" class="tgtSentence">Überprüfen Sie, ob die Projektdatei geändert wurde oder beschädigt ist.\</caps:sentence>  \<caps:sentence id="tgt6" sentenceid="0bd35f9b1c4cd407bbf060ad25b5cee2" class="tgtSentence">Wenn sie geändert wurde oder beschädigt ist, öffnen Sie das Projekt in der <token>vsprvs</token>-Version, in der es erstellt wurde, speichern Sie es, und versuchen Sie dann erneut, es zu konvertieren.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerErrorMessageDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      <ui>
        \<caps:sentence id="src1" class="srcSentence">The file name of the old project must be specified.\</caps:sentence>
      </ui>
    </para>
        \<para xml:space="preserve">
      \<caps:sentence id="src2" class="srcSentence">This project file does not exist in the expected location.\</caps:sentence>
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
            \<caps:sentence id="src4" class="srcSentence">Check whether the project file has been moved.\</caps:sentence>
          </para>
            </content>
          </step>
          <step>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src5" class="srcSentence">Check whether the project file has been modified or corrupted.\</caps:sentence>  \<caps:sentence id="src6" class="srcSentence">If it has been modified or corrupted, open the project in the version of <token>vsprvs</token> in which it was created, save it, and then attempt to convert it again.\</caps:sentence>  </para>
            </content>
          </step>
        </steps>
      </procedure>
      <relatedTopics>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
      </relatedTopics>
    </developerErrorMessageDocument>
  \</caps:SxSSource>
\</caps:SxS>