---
title: Erstellen einer MFC-Anwendung im Webbrowserstil | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications, creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ccfb093a65c3f9a72b6180c4f415a92ebaf18684
ms.lasthandoff: 02/24/2017

---
# <a name="creating-a-web-browser-style-mfc-application"></a>Erstellen einer MFC-Anwendung im Webbrowserstil
Eine Web-Anwendung Webbrowserstil kann Informationen über das Internet (z. B. HTML oder active Documents) oder ein Intranet als auch Ordner im lokalen Dateisystem und im Netzwerk zugreifen. Durch Ableiten von der Anwendung Ansichtsklasse aus [CHtmlView](../../mfc/reference/chtmlview-class.md)effektiv Sie machen der Anwendung einen Webbrowser, indem Sie die Ansicht mit dem WebBrowser-Steuerelement bereitstellen.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>Erstellen eine Web-Browser-Anwendung basierend auf der MFC-Dokument-/ Ansichtarchitektur  
  
1.  Führen Sie die Schritte in [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Im MFC-Anwendung Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite, stellen Sie sicher, dass die **Dokument-/Ansichtarchitektur** aktiviert ist. (Sie haben die Wahl **Dokument** oder **mehrere Dokumente**, aber nicht **Dialogfeldern basierend**.)  
  
3.  Auf der [erstellte Klassen überprüfen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite der **Basisklasse** Dropdown-Menü auswählen `CHtmlView`.  
  
4.  Wählen Sie alle anderen gewünschten Optionen das Anwendungsgerüst integriert.  
  
5.  Klicken Sie auf **Fertig stellen**.  
  
 Das WebBrowser-Steuerelement unterstützt das Webbrowsen über Hyperlinks und Navigation der Uniform Resource Locator (URL). Das Steuerelement verwaltet eine Verlaufsliste, die dem Benutzer ermöglicht, Vorwärts navigieren und rückwärts durch vorher besucht haben Websites, Ordner und Dokumente. Die Navigation, Hyperlinks, Verlaufslisten, Favoriten und Sicherheit werden direkt über das Steuerelement verwaltet. Clientanwendungen können das WebBrowser-Steuerelement als active Document-Container zu Host als auch für aktive Dokumente verwenden. Folglich können aufwendig formatierte Dokumente, z. B. Microsoft Excel-Kalkulationstabellen oder Word-Dokumente geöffnet und bearbeitet werden direkt im WebBrowser-Steuerelement. Das WebBrowser-Steuerelement ist auch ein ActiveX-Steuerelementcontainer, der beliebige ActiveX-Steuerelemente hosten kann.  
  
> [!NOTE]
>  Der WebBrowser ActiveX-Steuerelement (und daher `CHtmlView`) steht nur für Anwendungen, die unter Windows-Versionen in der Internet Explorer 4.0 oder höher installiert wurde.  
  
 Da `CHtmlView` implementiert einfach das Microsoft Web-Browser-Steuerelement, die Unterstützung für das Drucken ist nicht wie andere [CView](../../mfc/reference/cview-class.md)-abgeleitete Klassen. Stattdessen implementiert das WebBrowser-Steuerelement der Benutzeroberfläche des Druckers und drucken. Daher `CHtmlView` ist keine Seitenansicht, und das Framework bietet keine weitere Unterstützung Druckfunktionen: z. B. [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), und [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), die in einer anderen MFC-Anwendung zur Verfügung stehen.  
  
 `CHtmlView`fungiert als Wrapper für das Webbrowser-Steuerelement, das wodurch Ihre Anwendung eine Ansicht auf eine Web- oder eine HTML-Seite erhält. Der Assistent erstellt eine Überschreibung der [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) -Funktion in der Ansichtsklasse, sodass ein Link zur Microsoft Visual C++-Website:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 Sie können diese Site durch eine eigene ersetzen oder können Sie die [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) Member-Funktion, um eine HTML-Seite zu öffnen, die im Ressourcenskript des Projekts als Standardinhalt für die Ansicht befindet. Zum Beispiel:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Bereitstellen von Anwendungen](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


