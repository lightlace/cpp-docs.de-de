---
title: Aktive Dokumente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a391dda8f8ffee6cec3cebc9d03250336195db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335502"
---
# <a name="active-documents"></a>Aktive Dokumente
Aktive Dokumente erweitern die Verbunddokument-Technologie von OLE. Diese Erweiterungen werden in Form von zusätzlichen Schnittstellen bereitgestellt, die Ansichten zu verwalten, damit Objekte in Containern funktionieren und noch behalten die Kontrolle über ihre anzeigen und Drucken Funktionen können. Dieser Prozess ermöglicht die Dokumente in fremden Frames (z. B. die Microsoft Office Binder oder Microsoft Internet Explorer) und in systemeigene Rahmen (z. B. das Anzeigen der Ports des Produkts) anzuzeigen.  
  
 In diesem Abschnitt wird beschrieben, die funktionale [Anforderungen für aktive Dokumente](#requirements_for_active_documents). Das aktive Dokument besitzt einen Satz von Daten und hat Zugriff auf Speicher, in dem die Daten gespeichert und abgerufen werden kann. Sie können erstellen und Verwalten einer oder mehreren Ansichten für seine Daten. Zusätzlich zur Unterstützung der üblichen einbetten und direkte Aktivierungsschnittstellen von OLE-Dokumente an, das aktive Dokument kommuniziert die Fähigkeit zum Erstellen von Sichten über `IOleDocument`. Über diese Schnittstelle kann der Container bitten, zum Erstellen (und möglicherweise aufzählen) die Ansichten, die das aktive Dokument angezeigt werden kann. Über diese Schnittstelle Geben Sie das aktive Dokument kann auch verschiedene Informationen über sich selbst, z. B., ob es sich um mehrere Ansichten oder komplexe Rechtecke unterstützt.  
  
 Im folgenden finden Sie die **IOleDocument** Schnittstelle. Beachten Sie, dass die **IEnumOleDocumentViews** Schnittstelle ist ein standard-OLE-Enumerator für **IOleDocumentView \***  Typen.  
  
```  
interface IOleDocument : IUnknown  
    {  
    HRESULT CreateView(  
        [in] IOleInPlaceSite *pIPSite,  
        [in] IStream *pstm,  
        [in] DWORD dwReserved,  
        [out] IOleDocumentView **ppView);  

    HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);  

    HRESULT EnumViews(  
        [out] IEnumOleDocumentViews **ppEnum,  
        [out] IOleDocumentView **ppView);  
    }  
```  
  
 Jede aktive Dokument muss ein sichtanbieter-Frame mit dieser Schnittstelle haben. Wenn das Dokument nicht innerhalb eines Containers eingebettet ist, muss der active Document-Server selbst den anzeigen-Frame angeben. Das aktive Dokument in einer active Document-Container eingebettet ist, bietet der Container jedoch den Rahmen anzeigen.  
  
 Ein aktiven Dokuments kann eine oder mehrere Arten von erstellen [Ansichten](#requirements_for_view_objects) seiner Daten (z. B. normaler Schrift, gliedern, Seitenlayouts usw.). Ansichten fungiert als Filter, die über die die Daten angezeigt werden. Auch wenn das Dokument nur eine Art von Ansicht hat, weiterhin empfiehlt mehrerer Ansichten zu unterstützen, als Mittel zur Unterstützung neuer Fenster-Funktionen (z. B. die **neues Fenster** Element auf der **Fenster** Menü in Office Anwendungen).  
  
##  <a name="requirements_for_active_documents"></a> Anforderungen für aktive Dokumente  
 Ein aktiven Dokuments, das in einer active Document-Container angezeigt werden muss:  
  
-   Verwenden des OLE-Verbunddateien als Speichermechanismus durch die Implementierung `IPersistStorage`.  
  
-   Unterstützt die grundlegenden Einbetten von Funktionen von OLE-Dokumente, einschließlich **aus Datei erstellen**. Dies erfordert, dass die Schnittstellen `IPersistFile`, `IOleObject`, und `IDataObject`.  
  
-   Eine oder mehrere Ansichten, von die jede direkte Aktivierung kann zu unterstützen. D. h. müssen die Ansichten die Schnittstelle unterstützen `IOleDocumentView` sowie die Schnittstellen `IOleInPlaceObject` und `IOleInPlaceActiveObject` (unter Verwendung des Containers **IOleInPlaceSite** und **IOleInPlaceFrame** Schnittstellen).  
  
-   Unterstützt die standardmäßigen active Document-Schnittstellen `IOleDocument`, `IOleCommandTarget`, und `IPrint`.  
  
 Wissen, wann und wie Sie die Container-Seite-Schnittstellen verwenden, wird in diese Anforderungen impliziert.  
  
##  <a name="requirements_for_view_objects"></a> Anforderungen für die Objekte anzeigen  
 Ein aktiven Dokuments kann eine oder mehrere Ansichten für seine Daten erstellen. Funktionell sind diese Sichten wie Ports für eine bestimmte Methode zum Anzeigen der Daten. Wenn ein aktiven Dokuments nur eine einzige Ansicht unterstützt, können das aktive Dokument und die einzelne Ansicht mit einer einzelnen Klasse implementiert werden. **IOleDocument:: CreateView** gibt des gleichen Objekts `IOleDocumentView` Schnittstellenzeiger auf.  
  
 Um in einer active Document-Container dargestellt werden, muss eine Ansichtskomponente unterstützen **IOleInPlaceObject** und **IOleInPlaceActiveObject** zusätzlich zu `IOleDocumentView`:  
  
```  
interface IOleDocumentView : IUnknown  
    {  
    HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);  
    HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);  
    HRESULT GetDocument([out] IUnknown **ppunk);  
    [input_sync] HRESULT SetRect([in] LPRECT prcView);  
    HRESULT GetRect([in] LPRECT prcView);  
    [input_sync] HRESULT SetRectComplex(  
        [in] LPRECT prcView,  
        [in] LPRECT prcHScroll,  
        [in] LPRECT prcVScroll,  
        [in] LPRECT prcSizeBox);  
    HRESULT Show([in] BOOL fShow);  
    HRESULT UIActivate([in] BOOL fUIActivate);  
    HRESULT Open(void);  
    HRESULT CloseView([in] DWORD dwReserved);  
    HRESULT SaveViewState([in] IStream *pstm);  
    HRESULT ApplyViewState([in] IStream *pstm);  
    HRESULT Clone(  
        [in] IOleInPlaceSite *pIPSiteNew,  
        [out] IOleDocumentView **ppViewNew);  
    }  
```  
  
 Jede Ansicht verfügt über eine zugeordnete Ansicht-Standort, der Sicht Frames und der Viewport (HWND und eines rechteckigen Bereichs, in diesem Fenster) kapselt. Die Website verfügbar macht diese Funktionalität jedoch den Standard **IOleInPlaceSite** Schnittstelle. Beachten Sie, dass es möglich ist, haben mehr als einen Viewport auf eine einzelne HWND.  
  
 Normalerweise weist jede Art von Ansicht eine andere gedruckte Darstellung. Daher Ansichten und die dazugehörigen Ansicht Standorte sollten die Drucken-Schnittstellen implementieren Wenn `IPrint` und `IContinueCallback`zugeordnet. Der Rahmen anzeigen muss mit dem Anbieter Ansicht über aushandeln **IPrint** bei Beginn des Druckens, sodass Kopfzeilen, Fußzeilen, Seitenränder und verwandten Elementen ordnungsgemäß gedruckt werden. Benachrichtigt den Frame des Drucken-bezogene Ereignisse über die Ansicht-Anbieter `IContinueCallback`. Weitere Informationen zur Verwendung dieser Schnittstellen, finden Sie unter [programmgesteuerten Drucken](../mfc/programmatic-printing.md).  
  
 Beachten Sie, dass wenn ein aktive Dokument nur eine einzige Ansicht unterstützt klicken Sie dann das aktive Dokument und die einzelne Ansicht implementiert werden können mithilfe einer einzigen konkreten Klasse. **IOleDocument:: CreateView** einfach gibt des gleichen Objekts `IOleDocumentView` Schnittstellenzeiger auf. Kurz gesagt, ist es nicht notwendig, die zwei separate Objektinstanzen vorhanden sein, wenn nur eine Ansicht erforderlich ist.  
  
 Ein Objekt kann auch ein Befehlsziel sein. Durch die Implementierung `IOleCommandTarget` eine Sicht kann empfangen von Befehlen, die in der Benutzeroberfläche des Containers stammen (z. B. **neu**, **öffnen**, **speichern unter**,  **Drucken** auf die **Datei** Menü; und **Kopie**, **einfügen**, **Rückgängig** auf die **Bearbeiten** Menü). Weitere Informationen finden Sie unter [Nachrichtenbehandlung und Befehlsziele](../mfc/message-handling-and-command-targets.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)

