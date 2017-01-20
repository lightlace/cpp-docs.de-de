---
title: "Problembehandlung bei Ausnahmen: System.Messaging.MessageQueueException"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Meldungswarteschlangen, Ausnahmen"
  - "MessageQueueException-Klasse"
  - "Ausnahmen, Meldungswarteschlangen"
ms.assetid: 101cf1df-ce09-4c61-b671-975a7c3f6139
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.Messaging.MessageQueueException
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget locale="de-DE">
    \<developerTroubleshootingDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          \<caps:sentence sentenceid="99020cb24bd13238d907c65cc2b57c03" id="tgt1" class="tgtSentence">Eine <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>-Ausnahme wird ausgelöst, wenn ein interner Fehler von Microsoft Message Queuing auftritt.\</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence sentenceid="8fb38e47cd8f7d68c13dba707beeb671" id="tgt2" class="tgtSentence">Tipps\</caps:sentence>
        </title>
        <content>
          <definitionTable>
            <definedTerm>
              <ui>
                \<caps:sentence sentenceid="e99e23828540dd6f562c676a32b9b0be" id="tgt3" class="tgtSentence">Überprüfen Sie die MessageQueueErrorCode-Eigenschaft der Ausnahme, um zu bestimmen, warum die MessageQueue-Operation fehlgeschlagen ist.\</caps:sentence>
              </ui>
            </definedTerm>
            <definition>
              <para>
                \<caps:sentence sentenceid="81d4b465de81bc1e6778980d2e2e805f" id="tgt4" class="tgtSentence">Der <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>-Klasse zugeordnete Ausnahmen werden von internen Fehlern von Message Queueing generiert, die programmgesteuert behandelt werden sollten.\</caps:sentence>
                \<caps:sentence sentenceid="e24b951c22c6585e9f980820d5c37311" id="tgt5" class="tgtSentence"> Jede Ausnahme besteht aus einem Fehlercode und einer Textzeichenfolge, die die Quelle beschreibt.\</caps:sentence>
                \<caps:sentence sentenceid="c699a2f7221e07573e72294535652e36" id="tgt6" class="tgtSentence"> Eine Liste mit diesen Fehlercodes und ihren Beschreibungen finden Sie unter <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueErrorCode</codeEntityReference>.\</caps:sentence>
              </para>
            </definition>
          </definitionTable>
        </content>
        <sections>
          <section>
            <title>
              \<caps:sentence sentenceid="46b83674d1a52e84f8c820eb64c53574" id="tgt7" class="tgtSentence">Hinweise\</caps:sentence>
            </title>
            <content>
              <para>
                \<caps:sentence sentenceid="56838c41ae304bfa568f8f06e207ddb4" id="tgt8" class="tgtSentence">Wenn eine <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> eine Warteschlange öffnet und der <parameterReference>sharedModeDenyReceive</parameterReference>-Parameter dabei auf true festgelegt ist, wird durch jeden späteren Versuch einer <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference>, Daten aus der Warteschlange zu lesen, wegen der Freigabeverletzung eine <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>-Ausnahme generiert.\</caps:sentence>
                \<caps:sentence sentenceid="3542828156eabd35af17b04b77ff90fe" id="tgt9" class="tgtSentence"> Diese Ausnahme wird ebenso ausgelöst, wenn eine <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> versucht, im exklusiven Modus auf die Warteschlange zuzugreifen, während eine andere <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> bereits nicht exklusiven Zugriff auf die Warteschlange hat.\</caps:sentence>
              </para>
              <alert class="visual basic note">
                <para>
                  \<caps:sentence sentenceid="0d8eaea8fc7e9560d0dd0a91e2db02d5" id="tgt10" class="tgtSentence">
                    <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueTransaction</codeEntityReference> ist abhängig vom Threadapartmentstatus.\</caps:sentence>
                  \<caps:sentence sentenceid="67c6ef965e868d7e3a9ca2ca85fb10bc" id="tgt11" class="tgtSentence"> Visual Basic legt den Zustand des Hauptthreads auf <languageKeyword>STA</languageKeyword> fest. Deshalb müssen Sie in der <codeEntityReference autoUpgrade="true">T:System.MTAThreadAttribute</codeEntityReference>-Unterroutine das <codeInline> Main </codeInline> anwenden.\</caps:sentence>
                  \<caps:sentence sentenceid="aba866c4bc559ce565c3e0c432161c5c" id="tgt12" class="tgtSentence"> Andernfalls wird durch das Senden einer Transaktionsmeldung mithilfe eines anderen Threads eine <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>-Ausnahme ausgelöst.\</caps:sentence>
                </para>
              </alert>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>
        \<link xlink:href="e0a78c50-7318-4d54-af51-40c00aea8711">How to: Find Out More About an Exception with the Exception Assistant</link>
      </relatedTopics>
    </developerTroubleshootingDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource locale="en-US">
    \<developerTroubleshootingDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          \<caps:sentence id="src1" class="srcSentence">A <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference> exception is thrown if a Microsoft Message Queuing internal error occurs.\</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="src2" class="srcSentence">Associated Tips\</caps:sentence>
        </title>
        <content>
          <definitionTable>
            <definedTerm>
              <ui>
                \<caps:sentence id="src3" class="srcSentence">Check the MessageQueueErrorCode property of the exception to determine why the MessageQueue operation failed.\</caps:sentence>
              </ui>
            </definedTerm>
            <definition>
              <para>
                \<caps:sentence id="src4" class="srcSentence">Exceptions associated with the <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference> class are generated by internal errors within Message Queueing that should be dealt with programmatically.\</caps:sentence>
                \<caps:sentence id="src5" class="srcSentence"> Every exception consists of an error code and a text string that describes the source.\</caps:sentence>
                \<caps:sentence id="src6" class="srcSentence"> For a list of these error codes and their descriptions, see <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueErrorCode</codeEntityReference>.\</caps:sentence>
              </para>
            </definition>
          </definitionTable>
        </content>
        <sections>
          <section>
            <title>
              \<caps:sentence id="src7" class="srcSentence">Remarks\</caps:sentence>
            </title>
            <content>
              <para>
                \<caps:sentence id="src8" class="srcSentence">If a <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> opens a queue with the <parameterReference>sharedModeDenyReceive</parameterReference> parameter set to true, any <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> that subsequently tries to read from the queue generates a <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference> exception because of a sharing violation.\</caps:sentence>
                \<caps:sentence id="src9" class="srcSentence"> The same exception is thrown if a <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> tries to access the queue in exclusive mode while another <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueue</codeEntityReference> already has nonexclusive access to the queue.\</caps:sentence>
              </para>
              <alert class="visual basic note">
                <para>
                  \<caps:sentence id="src10" class="srcSentence">
                    <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueTransaction</codeEntityReference> is threading-apartment–aware.\</caps:sentence>
                  \<caps:sentence id="src11" class="srcSentence"> Visual Basic sets the state of the main thread to <languageKeyword>STA</languageKeyword>, so you must apply the <codeEntityReference autoUpgrade="true">T:System.MTAThreadAttribute</codeEntityReference> in the<codeInline> Main </codeInline>subroutine.\</caps:sentence>
                  \<caps:sentence id="src12" class="srcSentence"> Otherwise, sending a transactional message using another thread throws a <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference> exception.\</caps:sentence>
                </para>
              </alert>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <codeEntityReference autoUpgrade="true">T:System.Messaging.MessageQueueException</codeEntityReference>
        \<link xlink:href="e0a78c50-7318-4d54-af51-40c00aea8711">How to: Find Out More About an Exception with the Exception Assistant</link>
      </relatedTopics>
    </developerTroubleshootingDocument>
  \</caps:SxSSource>
\</caps:SxS>