---
title: "Erstellen einer MFC-Anwendung im Webbrowserstil"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcweb.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, Webanwendungen"
  - "Webanwendungen, Erstellen"
  - "Webbrowser"
  - "Webbrowser, Erstellen aus MFC-Architektur"
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen einer MFC-Anwendung im Webbrowserstil
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Anwendung im Webbrowserstil kann auf Informationen im Internet \(z. B. auf HTML\-Daten oder Active Documents\) oder in einem Intranet genauso zugreifen wie auf Ordner im lokalen Dateisystem und im Netzwerk.  Wenn Sie die Ansichtsklasse der Anwendung von [CHtmlView](../../mfc/reference/chtmlview-class.md) ableiten, können Sie die Anwendung auf effiziente Weise als Webbrowser entwickeln, indem Sie die Ansicht mit dem WebBrowser\-Steuerelement bereitstellen.  
  
### So erstellen Sie eine Webbrowseranwendung, die auf der Dokument\-\/Ansichtarchitektur von MFC basiert  
  
1.  Folgen Sie den Anweisungen unter [Erstellen einer MFC\-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Stellen Sie sicher, dass auf der Seite [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten das Kontrollkästchen **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert ist. \(Sie können **Einfaches Dokument** oder **Mehrfaches Dokument** auswählen, nicht aber **Auf Dialogfeldern basierend**.\)  
  
3.  Verwenden Sie auf der Seite [Erstellte Klassen überprüfen](../../mfc/reference/generated-classes-mfc-application-wizard.md) das Dropdownmenü **Basisklasse**, um `CHtmlView` auszuwählen.  
  
4.  Wählen Sie ggf. weitere Optionen aus, die in die Skelettanwendung integriert werden sollen.  
  
5.  Klicken Sie auf **Fertig stellen**.  
  
 Das WebBrowser\-Steuerelement unterstützt die Suche im Web über Links sowie über die URL \(Uniform Resource Locator\)\-Navigation.  Das Steuerelement verwaltet eine Verlaufsliste, mit deren Hilfe der Benutzer bereits aufgesuchte Sites, Ordner und Dokumente vorwärts und rückwärts durchsuchen kann.  Navigation, Links, Verlaufslisten, Favoriten und Sicherheit werden direkt über das Steuerelement verwaltet.  Anwendungen können das WebBrowser\-Steuerelement auch als Active Document\-Container verwenden, der die Active Documents enthält.  Auf diese Weise können aufwendig formatierte Dokumente, z. B. Microsoft Excel\-Arbeitsblätter oder Word\-Dokumente, direkt im WebBrowser\-Steuerelement geöffnet und bearbeitet werden.  Das WebBrowser\-Steuerelement ist zusätzlich ein ActiveX\-Steuerelementcontainer, der beliebige ActiveX\-Steuerelemente aufnehmen kann.  
  
> [!NOTE]
>  Das WebBrowser\-ActiveX\-Steuerelement \(und somit `CHtmlView`\) ist nur für Anwendungen verfügbar, die unter Windows\-Versionen mit Internet Explorer 4.0 \(oder höher\) ausgeführt werden.  
  
 Da durch `CHtmlView` einfach das WebBrowser\-Steuerelement von Microsoft implementiert wird, unterstützt das Steuerelement die Druckfeatures nicht in dem Umfang wie andere von [CView](../../mfc/reference/cview-class.md) abgeleitete Klassen.  Das WebBrowser\-Steuerelement implementiert stattdessen die Benutzeroberfläche für den Drucker und Druckfeatures.  Aus diesem Grund unterstützt `CHtmlView` keine Seitenansicht, und das Framework bietet auch keine darüber hinausgehenden Funktionen für die Druckunterstützung, wie [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md) und [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md), die beispielsweise in anderen MFC\-Anwendungen verfügbar sind.  
  
 Die `CHtmlView`\-Klasse fungiert als Wrapper für das WebBrowser\-Steuerelement, wodurch Ihre Anwendung eine Ansicht auf eine Web\- bzw. HTML\-Seite erhält.  Der Assistent überschreibt die [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)\-Funktion in der Ansichtsklasse, sodass ein Link zur Microsoft Visual C\+\+\-Website hergestellt wird:  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),NULL,NULL);  
}  
```  
  
 Sie können diese Site durch eine eigene Site ersetzen oder mithilfe der Memberfunktion [LoadFromResource](../Topic/CHtmlView::LoadFromResource.md) eine HTML\-Seite öffnen, die im Ressourcenskript des Projekts als Standardinhalt für die Ansicht aufgeführt ist.  Beispiel:  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   LoadFromResource(IDR_HTML1);  
}  
```  
  
## Siehe auch  
 [MFC Sample MFCIE](assetId:///7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Deploying Applications](assetId:///4ff8881d-0daf-47e7-bfe7-774c625031b4)