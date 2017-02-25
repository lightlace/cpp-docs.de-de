---
title: "Aktive Dokumente | Microsoft Docs"
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
  - "Aktive Dokumente [C++]"
  - "Aktive Dokumente [C++], Anforderungen"
  - "Aktive Dokumente [C++], Ansichten"
  - "OLE [C++], Aktive Dokumente"
  - "View-Objekte, Anforderungen"
  - "Ansichten [C++], Aktive Dokumente"
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Aktive Dokumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active Documents erweitern die Verbunddokumenttechnologie von OLE.  Diese Erweiterungen werden in Form zusätzlicher Schnittstellen bereitgestellt, die Ansichten verwalten, sodass Objekte in Containern arbeiten bei Steuerelement über ihre um Anzeige und Druck beibehalten können.  Dieser Prozess ist es möglich, Dokumente in der fremden Frames \(wie das Microsoft Office\-Binder oder in Microsoft Internet Explorer\) sowie in systemeigenen Frames anzuzeigen \(z eigenen Anzeigebereichen des Produkts\).  
  
 Dieser Abschnitt beschreibt funktionale [Anforderungen für aktive Dokumente](#requirements_for_active_documents).  Das aktive Dokument besitzt eine Datenmenge und hat Zugriff den Speicher, in dem die Daten gespeichert und abgerufen werden können.  Es kann eine oder mehrere Ansichten auf die Daten erstellen und verwalten.  Zusätzlich zur Unterstützung der üblichen Einbettungs\- und Aktivierungsschnittstellen von OLE\-Dokumenten, teilt das aktive Dokument mit der Fähigkeit, Ansichten durch `IOleDocument` zu erstellen.  Durch diese Schnittstelle kann der Container anfordert, \(und möglicherweise auflisten\) die Ansichten zu erstellen, die das aktive Dokument anzeigen kann.  Durch diese Schnittstelle kann das aktive Dokument verschiedene Informationen über sich, z angeben, dass es mehrere oder komplexe Ansichten Rechtecke unterstützt.  
  
 Im Folgenden ist die Schnittstelle **IOleDocument** .  Beachten Sie, dass die **IEnumOleDocumentViews**\-Schnittstelle ein Enumerator standardmäßigen OLE für **IOleDocumentView \***\-Typen ist.  
  
 `interface IOleDocument : IUnknown`  
  
 `{`  
  
 `HRESULT CreateView(`  
  
 `[in] IOleInPlaceSite *pIPSite,`  
  
 `[in] IStream *pstm,`  
  
 `[in] DWORD dwReserved,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);`  
  
 `HRESULT EnumViews(`  
  
 `[out] IEnumOleDocumentViews **ppEnum,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `}`  
  
 Jedes aktive Dokument muss einen Ansichtsframeanbieter mit dieser Schnittstelle haben.  Wenn das Dokument nicht innerhalb eines Containers eingebettet ist, muss der Active Document\-Server selbst die Ansichtsframe bereitstellen.  Wenn das aktive Dokument auf einem Active Document\-Container eingebettet wird, stellt der Container die Ansichtsframe.  
  
 Ein aktives Dokument kann eine oder mehrere [Ansichten](#requirements_for_view_objects)\-Typen der Daten \(beispielsweise, Normal, Gliederung, Seitenlayout, usw. erstellen.\).  Ansichten verhalten sich wie Filter, durch die die Daten angezeigt werden können.  Auch wenn das Dokument nur einen Typ Ansicht enthält, können Sie weiterhin mehrere Ansichten als Möglichkeit der Unterstützung der Funktionalität des neuen Fensters \(beispielsweise, das **Neues Fenster** \-Element im Menü **Fenster** in Office\-Anwendungen\) unterstützen.  
  
##  <a name="requirements_for_active_documents"></a> Anforderungen für aktive Dokumente  
 Ein aktives Dokument, das auf einem Active Document\-Container angezeigt werden kann, muss:  
  
-   Verwenden Sie Verbunddateien OLE als Speichermechanismus, indem Sie `IPersistStorage` implementieren.  
  
-   Unterstützen Sie die grundlegenden Einbettungsfunktionen von OLE\-Dokumenten, einschließlich **Von Datei erstellen**.  Dies erfordert die Schnittstellen `IPersistFile`, `IOleObject` und `IDataObject`.  
  
-   Unterstützen Sie eine oder mehrere Ansichten, von denen jede zur direkten Aktivierung kann.  Das bedeutet, dass die Ansichten die Schnittstelle `IOleDocumentView` sowie die Schnittstellen `IOleInPlaceObject` und `IOleInPlaceActiveObject` unterstützen \(mithilfe des Containers und  **IOleInPlaceSite** der **IOleInPlaceFrame**\-Schnittstellen\).  
  
-   Unterstützen Sie die aktiven StandardDokumentoberflächen `IOleDocument`, `IOleCommandTarget` und `IPrint`.  
  
 Kenntnisse der, wann und wie die ContainerSeitenschnittstellen gilt in diesen Anforderungen verwendet.  
  
##  <a name="requirements_for_view_objects"></a> Anforderungen für View\-Objekte  
 Ein aktives Dokument kann eine oder mehrere Ansichten der Daten erstellen.  Funktionell Diese Ansichten sind wie Ports auf eine bestimmte Methode zum Anzeigen der Daten.  Wenn ein aktives Dokument nur einer einzelnen Ansicht unterstützt, können das aktive Dokument und diese einzelne Ansicht mit einer einzelnen Klasse implementiert werden.  **IOleDocument::CreateView** gibt den gleichen `IOleDocumentView`\-Schnittstellenzeiger des Objekts zurück.  
  
 So unterstützen innerhalb eines Active Document\-Container dargestellt zu werden, muss eine Ansichtskomponente **IOleInPlaceObject**  und **IOleInPlaceActiveObject**  zusätzlich zu `IOleDocumentView`:  
  
 `interface IOleDocumentView : IUnknown`  
  
 `{`  
  
 `HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);`  
  
 `HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);`  
  
 `HRESULT GetDocument([out] IUnknown **ppunk);`  
  
 `[input_sync] HRESULT SetRect([in] LPRECT prcView);`  
  
 `HRESULT GetRect([in] LPRECT prcView);`  
  
 `[input_sync] HRESULT SetRectComplex(`  
  
 `[in] LPRECT prcView,`  
  
 `[in] LPRECT prcHScroll,`  
  
 `[in] LPRECT prcVScroll,`  
  
 `[in] LPRECT prcSizeBox);`  
  
 `HRESULT Show([in] BOOL fShow);`  
  
 `HRESULT UIActivate([in] BOOL fUIActivate);`  
  
 `HRESULT Open(void);`  
  
 `HRESULT CloseView([in] DWORD dwReserved);`  
  
 `HRESULT SaveViewState([in] IStream *pstm);`  
  
 `HRESULT ApplyViewState([in] IStream *pstm);`  
  
 `HRESULT Clone(`  
  
 `[in] IOleInPlaceSite *pIPSiteNew,`  
  
 `[out] IOleDocumentView **ppViewNew);`  
  
 `}`  
  
 Jede Ansicht enthält eine zugeordnete Ansichtssite, die die Ansichtsframe und kapselt den Viewport \(HWND und einen rechteckigen Bereich in diesem Fenster\).  Die Site macht diese Funktionalität obwohl die Standard\- **IOleInPlaceSite** \-Schnittstelle verfügbar.  Beachten Sie, dass es möglich ist, mehrere einen Anzeigebereich auf einzelnen HWND zu haben.  
  
 Normalerweise verfügt jeder Typ eine andere Ansicht gedruckte Darstellung.  Die Ansichten und die entsprechenden Ansichtssites sollten die Druckschnittstellen implementieren wenn `IPrint` und `IContinueCallback`, verwendet.  Die Ansichtsframe müssen mit dem Ansichtsanbieter von **IPrint** , wenn das Drucken aushandeln beginnt, sodass Kopfzeilen, Fußzeilen, Ränder und zugehörige Elemente ordnungsgemäß gedruckt werden.  Der Ansichtsanbieter benachrichtigt die Frames von Druck\-verknüpften Ereignisse von `IContinueCallback`.  Weitere Informationen zur Verwendung dieser Schnittstellen, finden Sie unter [Programmgesteuertes Drucken](../mfc/programmatic-printing.md).  
  
 Beachten Sie, dass wenn ein aktives Dokument nur einer einzelnen Ansicht, dann das aktive Dokument unterstützt und dass einzelne Ansicht mit einer einzelnen konkreten Klasse implementiert werden.  **IOleDocument::CreateView** gibt einfach denselben `IOleDocumentView`\-Schnittstellenzeiger des Objekts zurück.  Kurz gesagt ist es nicht notwendig, dass es zwei verschiedene Objektinstanzen gibt, wenn nur eine Ansicht erforderlich ist.  
  
 Ein View\-Objekt kann ein Befehlsziel auch sein.  Wenn `IOleCommandTarget` implementiert, kann eine Ansicht Befehle empfangen, die aus der Benutzeroberfläche des Containers stammen \(wie **Neu**, **Öffnen**, **Speichern unter**, **Drucken** im Menü **Datei** ; und **Kopieren**, **Einfügen**, **Rückgängig** im Menü **Bearbeiten** \).  Weitere Informationen finden Sie unter [Meldungsbehandlung und Befehlsziele](../mfc/message-handling-and-command-targets.md).  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containment.md)