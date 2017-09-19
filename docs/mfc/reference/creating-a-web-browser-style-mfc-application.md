---
title: Erstellen einer MFC-Anwendung im Webbrowserstil | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: da53bdff088c336b0e7eb33c49025ec0a48675f2
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="creating-a-web-browser-style-mfc-application"></a>Erstellen einer MFC-Anwendung im Webbrowserstil
Eine Web-Anwendung im Webbrowserstil kann Informationen aus dem Internet (z. B. HTML- oder aktive Dokumente) oder einem Intranet als auch Ordner im lokalen Dateisystem und in einem Netzwerk zugreifen. Durch Ableiten von der Anwendung Ansichtsklasse aus [CHtmlView](../../mfc/reference/chtmlview-class.md)effektiv Sie machen der Anwendung einen Webbrowser, indem Sie die Ansicht mit dem WebBrowser-Steuerelement bereitstellen.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>So erstellen eine Webbrowseranwendung, basierend auf die MFC-Dokument-/ Ansichtarchitektur  
  
1.  Befolgen Sie die Anweisungen im [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Im MFC-Anwendungs-Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite, stellen Sie sicher, dass die **Dokument-/Ansichtarchitektur** aktiviert ist. (Stehen Ihnen beide **einzelnes Dokument** oder **mehrere Dokumente**, aber nicht **Dialogfeldern basierend**.)  
  
3.  Auf der [Überprüfung generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite der **Basisklasse** Dropdown-Menü auswählen `CHtmlView`.  
  
4.  Wählen Sie alle anderen gewünschten Optionen die skelettanwendung integriert.  
  
5.  Klicken Sie auf **Fertig stellen**.  
  
 Das WebBrowser-Steuerelement unterstützt das Browsen im Internet über Hyperlinks und Navigation der Uniform Resource Locator (URL). Das Steuerelement unterhält eine Verlaufsliste, die dem Benutzer ermöglicht, Vorwärts navigieren und besuchte Websites, Ordner und Dokumente zuvor rückwärts durch. Das Steuerelement verwaltet direkt, die Navigation, links, Verlaufslisten, Favoriten und Sicherheit. Anwendungen können das WebBrowser-Steuerelement als active Document-Container auf dem Host als auch für aktive Dokumente verwenden. Folglich können formatierungsmöglichkeiten Dokumente wie z. B. Microsoft Excel-Kalkulationstabellen oder Word-Dokumente geöffnet und bearbeitet werden direkt in das WebBrowser-Steuerelement. Das WebBrowser-Steuerelement ist auch ein ActiveX-Steuerelementcontainer, der alle ActiveX-Steuerelement gehostet werden kann.  
  
> [!NOTE]
>  Der WebBrowser ActiveX-Steuerelement (und daher `CHtmlView`) steht nur für Anwendungen, die unter Windows-Versionen, in denen Internet Explorer 4.0 oder höher installiert wurde.  
  
 Da `CHtmlView` implementiert einfach die Microsoft Web Browsersteuerelement an, die Unterstützung für das Drucken ist nicht wie andere [CView](../../mfc/reference/cview-class.md)-abgeleitete Klassen. Das WebBrowser-Steuerelement implementiert stattdessen die Benutzeroberfläche des Druckers und den Druckvorgang. Daher `CHtmlView` wird nicht unterstützt, Seitenansicht, und das Framework bietet keine für andere drucken Unterstützungsfunktionen: z. B. [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), und [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), die in anderen MFC-Anwendungen verfügbar sind.  
  
 `CHtmlView`Dient als Wrapper für das Webbrowser-Steuerelement, das Ihre Anwendung in einer Web- oder eine HTML-Seite angezeigt gewährt. Der Assistent erstellt eine Überschreibung der [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) -Funktion in Ansichtsklasse, sodass ein Link auf der Website von Microsoft Visual C++:  
  
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
  
 Sie können diesen Standort mit einem Ihrer Wahl ersetzen oder können Sie die [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) Memberfunktion versucht, eine HTML-Seite zu öffnen, die als den Standardinhalt für die Ansicht des Projekts Ressourcenskript befindet. Zum Beispiel:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel-MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Bereitstellen von Anwendungen](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


