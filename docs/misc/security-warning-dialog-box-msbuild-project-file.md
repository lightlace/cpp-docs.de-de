---
title: "Dialogfeld &quot;Sicherheitswarnung&quot; (MSBuild-Projektdatei)"
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
  - "vs.projectfileinsecure"
helpviewer_keywords: 
  - "Sicherheitswarnung (Dialogfeld) [MSBuild-Projektdatei]"
  - "MSBuild, Sicherheitswarnung (Dialogfeld)"
ms.assetid: ea705296-ad5b-4e55-a75f-e421f35fe640
caps.latest.revision: 13
caps.handback.revision: "10"
ms.author: "mblome"
manager: "douge"
---
# Dialogfeld &quot;Sicherheitswarnung&quot; (MSBuild-Projektdatei)
\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerUIReferenceDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt1" sentenceid="946071f55e6dd0866d8b59bbee803eb3" class="tgtSentence">Das Dialogfeld <ui>Sicherheitswarnung</ui> warnt Entwickler hinsichtlich Sicherheitsproblemen bei Projekten.\</caps:sentence>
    </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="tgt2" sentenceid="5fe66f76bd494f79ec7c97c70fecc5f5" class="tgtSentence">Benutzeroberflächenelemente\</caps:sentence>
        </title>
        <content>
          <definitionTable>
            <definedTerm>
              <ui>Warnung für jedes Projekt in der Projektmappe anzeigen</ui>
            </definedTerm>
            <definition>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt3" sentenceid="f7a5d164e6bd1e3bf0edc4bc2735df1b" class="tgtSentence">Aktivieren Sie diese Option, damit für jedes Projekt in der Projektmappe eine Aufforderung angezeigt wird.\</caps:sentence>  \<caps:sentence id="tgt4" sentenceid="749948afa077630b170dadf782c0095f" class="tgtSentence">Dies ist die Standardeinstellung.\</caps:sentence>  </para>
            </definition>
          </definitionTable>
        </content>
      </section>
      <section>
        <content />
        <sections>
          <section>
            <title>
              \<caps:sentence id="tgt5" sentenceid="a799136c7384847654a8faf143fbb05c" class="tgtSentence">Projektelemente an möglicherweise gefährlichen Speicherorten\</caps:sentence>
            </title>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="tgt6" sentenceid="1d22d62b393acc8ea74396c5f33d595b" class="tgtSentence">Einige Elemente in normalerweise sicheren TARGETS-Dateien verwenden benutzerdefinierte Projekteigenschaften als Pfade.\</caps:sentence>  \<caps:sentence id="tgt7" sentenceid="aad13914d8adce5f054b5484fd6eb749" class="tgtSentence">Um zu verhindern, dass eine wichtige Datei durch ein Element überschrieben wird, werden Projektdateien mit Elementpfaden, die in eines der folgenden Verzeichnisse oder beliebige seiner Unterverzeichnisse ausgewertet werden, als mögliches Sicherheitsrisiko angesehen. Dies trifft nicht zu, wenn sich die Projektdateien ebenfalls im Projektmappendatei- oder Projektdateiverzeichnis oder einem seiner Unterverzeichnisse befinden.\</caps:sentence>  </para>
              <list class="bullet">
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="tgt8" sentenceid="4d430c400af470df662b6a3e4dd13f87" class="tgtSentence">Das Stammverzeichnis eines beliebigen Laufwerks\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="tgt9" sentenceid="5c33d0567fc750e4bf64a7c27a9853d5" class="tgtSentence">Das Windows-Verzeichnis, z. B. C:\Windows\.\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="tgt10" sentenceid="3bb194a87470309391bd1dfcb48b3e14" class="tgtSentence">Das Programmdateiverzeichnis, z. B. C:\Programme\.\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="tgt11" sentenceid="00d905de3f1fb59d8a71027525bb0626" class="tgtSentence">Netzwerkfreigaben.\</caps:sentence>
              </para>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="093395e1-70da-4f74-b34d-046c5e2b32e8">MSBuild Reference</link>
        \<link xlink:href="083b8ba3-e4ad-45af-bb5d-3bc81d406131">MSBuild Concepts</link>
      </relatedTopics>
    </developerUIReferenceDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerUIReferenceDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="src1" class="srcSentence">The <ui>Security Warning</ui> dialog box warns developers about security issues with projects.\</caps:sentence>
    </para>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="src2" class="srcSentence">UI Elements\</caps:sentence>
        </title>
        <content>
          <definitionTable>
            <definedTerm>
              <ui>Ask me for every project in this solution</ui>
            </definedTerm>
            <definition>
              \<para xml:space="preserve">
            \<caps:sentence id="src3" class="srcSentence">Select this option to be prompted for every project in the solution.\</caps:sentence>  \<caps:sentence id="src4" class="srcSentence">This is set by default.\</caps:sentence>  </para>
            </definition>
          </definitionTable>
        </content>
      </section>
      <section>
        <content />
        <sections>
          <section>
            <title>
              \<caps:sentence id="src5" class="srcSentence">Project Items in Potentially Dangerous Locations\</caps:sentence>
            </title>
            <content>
              \<para xml:space="preserve">
            \<caps:sentence id="src6" class="srcSentence">Some items in otherwise safe .targets files use user-defined project properties set their paths.\</caps:sentence>  \<caps:sentence id="src7" class="srcSentence">To prevent an item from overwriting an important file, project files that contain item paths that evaluate to one of the following locations or any subdirectories of these locations are considered to be potential security risks unless they are also located in or below the solution file or project file directory:\</caps:sentence>  </para>
              <list class="bullet">
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="src8" class="srcSentence">The root directory of any drive.\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="src9" class="srcSentence">The Windows directory, for example, C:\Windows\.\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="src10" class="srcSentence">The Program Files directory, for example, C:\Program Files\.\</caps:sentence>
              </para>
                </listItem>
                <listItem>
                  \<para xml:space="preserve">
                \<caps:sentence id="src11" class="srcSentence">Network shares.\</caps:sentence>
              </para>
                </listItem>
              </list>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        \<link xlink:href="e39f13f7-1e1d-4435-95ca-0c222bca071c">MSBuild</link>
        \<link xlink:href="093395e1-70da-4f74-b34d-046c5e2b32e8">MSBuild Reference</link>
        \<link xlink:href="083b8ba3-e4ad-45af-bb5d-3bc81d406131">MSBuild Concepts</link>
      </relatedTopics>
    </developerUIReferenceDocument>
  \</caps:SxSSource>
\</caps:SxS>