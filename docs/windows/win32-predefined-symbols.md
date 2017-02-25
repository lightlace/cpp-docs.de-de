---
title: "Win32 Predefined Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Win32 [C++], predefined symbols"
  - "symbols, Win32 predefined"
  - "Windows API [C++], predefined symbols"
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Win32 Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<?xml version="1.0" encoding="utf-8"?>
\<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  \<caps:SxSTarget>
    \<developerUIReferenceDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="tgt1" sentenceid="a3c3bb4ba61c2cce22ac9ea1e196c8a6" class="tgtSentence">Diese Symbole sind in den Win32-Headerdateien definiert und unterstützen Standardfunktionen und -aktionen von Windows-Anwendungen.\</caps:sentence>  \<caps:sentence id="tgt2" sentenceid="363ba2b48b0606ee3ddfe8a8314637e5" class="tgtSentence">Sie werden hauptsächlich zusammen mit allgemeinen UI-Elementen verwendet.\</caps:sentence>  \<caps:sentence id="tgt3" sentenceid="8470ee72124c9a86b67da768ad1f14ba" class="tgtSentence">Wenn Sie in den Ressourcen-Editoren mit Steuerelementen arbeiten, werden diese Symbole zusammen mit allgemeinen Steuerelementen im \<legacyLink xlink:href="E6E0FA4F-75C4-4A52-AF15-281CD61876CA">Eigenschaftenfenster</legacyLink> angezeigt.\</caps:sentence>  \<caps:sentence id="tgt4" sentenceid="d417a63bf07bf3aba7cb893c569566de" class="tgtSentence">Wenn in der Symbolleiste z. B. das Anwendungssymbol angezeigt werden soll, wird das Symbol im Eigenschaftenfenster mit dem Symbol <legacyBold>IDI_SMALL</legacyBold> verknüpft.\</caps:sentence>  </para>
        <table>
          <tbody>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt5" sentenceid="2d5d562e0617a9c71f851d42bad30bf3" class="tgtSentence">IDABORT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt6" sentenceid="90c78a528b6c1e87a04c69f1dcfc5b49" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <legacyBold>Abbrechen</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt7" sentenceid="f1c0892604842cba5b10364e268d86c2" class="tgtSentence">IDC_STATIC\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt8" sentenceid="aace68c599bdbda440f2f757bfbb627c" class="tgtSentence">Steuerelement: Statischer Text in einem Dialogfeld\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt9" sentenceid="577b9db13881c7f3b17264834032f580" class="tgtSentence">IDCANCEL\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt10" sentenceid="d09ae27778f6e8bed984f55e97929982" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <legacyBold>Abbrechen</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt11" sentenceid="55d0ff672e226d229e75c4a6e5db23ac" class="tgtSentence">IDD_ABOUTBOX\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt12" sentenceid="c97e57fea3782c4a6963693781f55f88" class="tgtSentence">Dialogfeld: Dialogfeld <legacyBold>Info</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt13" sentenceid="c54cd8e29d2e630ffb4081c4503bc433" class="tgtSentence">IDI_PROJECTNAME\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt14" sentenceid="4899024fdbefd713ef92e5dbfd5c5e80" class="tgtSentence">Symbol: Aktuelles Projektsymbol\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt15" sentenceid="fad7124576513f8157626661efb00911" class="tgtSentence">IDI_SMALL\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt16" sentenceid="afb249a2e45c57327fe72fa5e046be66" class="tgtSentence">Symbol: Kleines Symbol für aktuelles Projekt\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt17" sentenceid="c85fa61836a875fa18d83964ea6b7dab" class="tgtSentence">IDIGNORE\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt18" sentenceid="bd59ba89d73dd46ff97dee73c8367e1c" class="tgtSentence">Steuerelement: Wird in Dialogfeldern mit der Schaltfläche <legacyBold>Ignorieren</legacyBold> verwendet\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt19" sentenceid="c9502228fcb6329f48a1d9d2d2bbff2d" class="tgtSentence">IDM_ABOUT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt20" sentenceid="f688c7eff4b68c6e622e471692360510" class="tgtSentence">Menüelement: Wird mit <legacyBold>Hilfe</legacyBold>...<legacyBold>Info</legacyBold>... verwendet\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt21" sentenceid="fbfecd4d409be505aea85b3b95d0e8c4" class="tgtSentence">IDM_EXIT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt22" sentenceid="969e8f2bf62cdb81f6009339a4894701" class="tgtSentence">Menüelement: Wird mit <legacyBold>Datei</legacyBold>...<legacyBold>Beenden</legacyBold>... verwendet\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt23" sentenceid="fa16a68511ab7a579b8d5bdd8187b858" class="tgtSentence">IDNO\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt24" sentenceid="0116220b1644ef7267f13aa689f99da7" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <legacyBold>Nein</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt25" sentenceid="1f3536d9a44441e59286e4dd0dc54292" class="tgtSentence">IDOK\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt26" sentenceid="e4e7214314436a2748781bb403c0225e" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <UI>OK</UI>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt27" sentenceid="f6b9c78cf15eaf2f1d4c7f8363df9940" class="tgtSentence">IDRETRY\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt28" sentenceid="b082f6f30c7c6cba93f07d01ee934ba6" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <legacyBold>Wiederholen</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt29" sentenceid="96e2b8190e63ff088104b6ca8791632c" class="tgtSentence">IDS_APP_TITLE\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt30" sentenceid="3af703e99e7df74111bc77f5297cbbd7" class="tgtSentence">Zeichenfolge: Aktueller Anwendungsname\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt31" sentenceid="23fb726d5e87f7c774de9ffcebeb2c9a" class="tgtSentence">IDYES\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="tgt32" sentenceid="85faa776b7c2db2a0e979eb647d27030" class="tgtSentence">Steuerelement: Dialogfeld-Schaltfläche <legacyBold>Ja</legacyBold>\</caps:sentence>
            </para>
              </TD>
            </tr>
          </tbody>
        </table>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="tgt33" sentenceid="b4851e92b19af0c5c82447fc0937709d" class="tgtSentence">Anforderungen\</caps:sentence>
        </title>
        <content>
          \<para xml:space="preserve">
        \<caps:sentence id="tgt34" sentenceid="9c4f88f706dedde3bc0ebb66e34963e5" class="tgtSentence">Win32\</caps:sentence>
      </para>
        </content>
      </section>
      <relatedTopics>
        \<link xlink:href="91A5D610-1A04-47E8-B8A4-63AD650A90DF">Predefined Symbol IDs</link>
        \<link xlink:href="8FCCC09A-0237-4A65-B9C4-57D60C59E324">Symbols: Resource Identifiers</link>
      </relatedTopics>
    </developerUIReferenceDocument>
  \</caps:SxSTarget>
  \<caps:SxSSource>
    \<developerUIReferenceDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink">
      <introduction>
        \<para xml:space="preserve">
      \<caps:sentence id="src1" class="srcSentence">These symbols are defined in the Win32 header files, and they support standard Windows application functions and actions.\</caps:sentence>  \<caps:sentence id="src2" class="srcSentence">These symbols are mainly used with common UI elements.\</caps:sentence>  \<caps:sentence id="src3" class="srcSentence">When you are working with controls in the resource editors, these symbols will appear in the \<legacyLink xlink:href="E6E0FA4F-75C4-4A52-AF15-281CD61876CA">Properties Window</legacyLink> associated with common controls.\</caps:sentence>  \<caps:sentence id="src4" class="srcSentence">For instance, if your toolbar should display the application icon, the icon will be associated with the symbol IDI_SMALL in the Property Window.\</caps:sentence>  </para>
        <table>
          <tbody>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src5" class="srcSentence">IDABORT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src6" class="srcSentence">Control: Dialog box Abort button\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src7" class="srcSentence">IDC_STATIC\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src8" class="srcSentence">Control: Static text in a dialog box\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src9" class="srcSentence">IDCANCEL\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src10" class="srcSentence">Control: Dialog box Cancel button\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src11" class="srcSentence">IDD_ABOUTBOX\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src12" class="srcSentence">Dialog: Product About dialog box\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src13" class="srcSentence">IDI_PROJECTNAME\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src14" class="srcSentence">Icon: Current project icon\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src15" class="srcSentence">IDI_SMALL\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src16" class="srcSentence">Icon: Current project small icon\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src17" class="srcSentence">IDIGNORE\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src18" class="srcSentence">Control: Used with Ignore button on dialogs\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src19" class="srcSentence">IDM_ABOUT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src20" class="srcSentence">Menu Item: Used with Help...About...\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src21" class="srcSentence">IDM_EXIT\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src22" class="srcSentence">Menu Item: Used with File...Exit...\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src23" class="srcSentence">IDNO\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src24" class="srcSentence">Control: Dialog box No button\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src25" class="srcSentence">IDOK\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src26" class="srcSentence">Control: Dialog box OK button\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src27" class="srcSentence">IDRETRY\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src28" class="srcSentence">Control: Dialog box Retry button\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src29" class="srcSentence">IDS_APP_TITLE\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src30" class="srcSentence">String: Current application name\</caps:sentence>
            </para>
              </TD>
            </tr>
            <tr>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src31" class="srcSentence">IDYES\</caps:sentence>
            </para>
              </TD>
              <TD>
                \<para xml:space="preserve">
              \<caps:sentence id="src32" class="srcSentence">Control: Dialog box Yes button\</caps:sentence>
            </para>
              </TD>
            </tr>
          </tbody>
        </table>
      </introduction>
      <section>
        <title>
          \<caps:sentence id="src33" class="srcSentence">Requirements\</caps:sentence>
        </title>
        <content>
          \<para xml:space="preserve">
        \<caps:sentence id="src34" class="srcSentence">Win32\</caps:sentence>
      </para>
        </content>
      </section>
      <relatedTopics>
        \<link xlink:href="91A5D610-1A04-47E8-B8A4-63AD650A90DF">Predefined Symbol IDs</link>
        \<link xlink:href="8FCCC09A-0237-4A65-B9C4-57D60C59E324">Symbols: Resource Identifiers</link>
      </relatedTopics>
    </developerUIReferenceDocument>
  \</caps:SxSSource>
\</caps:SxS>