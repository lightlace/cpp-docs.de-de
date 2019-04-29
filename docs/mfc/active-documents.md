---
title: Aktive Dokumente
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
ms.openlocfilehash: 519dd51ab9b46adf862999104e97c6e478ccd86b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394948"
---
# <a name="active-documents"></a>Aktive Dokumente

Aktive Dokumente erweitern die Verbunddokument-Technologie von OLE. Diese Erweiterungen werden in Form von zusätzlichen Schnittstellen bereitgestellt, die Ansichten zu verwalten, damit Objekte in Containern funktionieren und noch behalten die Kontrolle über ihre anzeigen und Drucken Funktionen können. Dieser Prozess ermöglicht es, Dokumente in fremde Frames (z. B. der Microsoft Office Binder oder Microsoft Internet Explorer) und in nativen Frames (z. B. das Anzeigen der Ports des Produkts) angezeigt.

In diesem Abschnitt wird beschrieben, die funktionale [Anforderungen für aktive Dokumente](#requirements_for_active_documents). Das aktive Dokument besitzt einen Satz von Daten und hat Zugriff auf Speicher, in denen die Daten gespeichert und abgerufen werden kann. Sie erstellen und Verwalten einer oder mehreren Ansichten auf ihre Daten. Zusätzlich zur Unterstützung für die Einbettung und direkte Aktivierungsschnittstellen von OLE-Dokumente, kommuniziert das aktive Dokument die Möglichkeit zum Erstellen von Sichten über `IOleDocument`. Über diese Oberfläche lassen der Container zu erstellen (und ggf. die Enumeration) die Ansichten, die das aktive Dokument angezeigt werden kann. Über diese Schnittstelle bieten das aktive Dokument auch verschiedene Informationen über sich selbst, wie z. B., ob es sich um mehrere Ansichten oder komplexe Rechtecke unterstützt.

Im folgenden finden Sie die `IOleDocument` Schnittstelle. Beachten Sie, dass die `IEnumOleDocumentViews` Schnittstelle ist ein standard-OLE-Enumerator für `IOleDocumentView*` Typen.

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

Alle aktiven Dokument muss ein sichtanbieter-Frame mit dieser Schnittstelle haben. Wenn das Dokument nicht innerhalb eines Containers eingebettet ist, muss die active Document-Server selbst die Ansichtsframe angeben. Wenn das aktive Dokument in einem Container aktive Dokument eingebettet ist, bietet jedoch der Container der Frame anzeigen.

Erstellen Sie ein aktiven Dokuments kann einen oder mehrere Typen von [Ansichten](#requirements_for_view_objects) Daten (z. B. normal, gliedern, Seitenlayouts, usw.). Ansichten dienen, wie Filter, die über den die Daten angezeigt werden. Selbst wenn das Dokument nur eine Art von Ansicht verfügt, Sie können weiterhin mehrere Ansichten als Mittel zur Unterstützung neuer Funktionen für Fenster unterstützen möchten (z. B. die **neues Fenster** Element auf der **Fenster** Menü in Office Anwendungen).

##  <a name="requirements_for_active_documents"></a> Anforderungen für aktive Dokumente

Müssen eine aktive Dokument, das in einer active Document-Container angezeigt werden kann:

- Verwenden des OLE-Verbunddateien als Speichermechanismus, durch die Implementierung `IPersistStorage`.

- Unterstützt die grundlegende Einbettungsfunktionen von OLE-Dokumente, einschließlich **aus Datei erstellen**. Dies erfordert, dass die Schnittstellen `IPersistFile`, `IOleObject`, und `IDataObject`.

- Unterstützt eine oder mehrere Ansichten, von die jeder die direkte Aktivierung kann. Unterstützen, also die Ansichten müssen die Schnittstelle `IOleDocumentView` sowie die Schnittstellen `IOleInPlaceObject` und `IOleInPlaceActiveObject` (mithilfe des Containers `IOleInPlaceSite` und `IOleInPlaceFrame` Schnittstellen).

- Die standardmäßigen active Document-Schnittstellen unterstützen `IOleDocument`, `IOleCommandTarget`, und `IPrint`.

Wissen, wann und wie Sie die Container-Seite-Schnittstellen zu verwenden, wird diese Anforderungen impliziert.

##  <a name="requirements_for_view_objects"></a> Anforderungen für die Objekte anzeigen

Ein aktives Dokument kann eine oder mehrere Ansichten der Daten erstellen. Funktionell sind diese Ansichten wie Ports für eine bestimmte Methode zum Anzeigen der Daten ein. Wenn ein aktives Dokument nur eine einzigen Ansicht unterstützt, können das aktive Dokument und die einzelne Ansicht über eine einzelne Klasse implementiert werden. `IOleDocument::CreateView` Gibt zurück, des gleichen Objekts `IOleDocumentView` Schnittstellenzeiger auf.

Um in einer active Document-Container dargestellt werden, muss eine Ansichtskomponente unterstützen `IOleInPlaceObject` und `IOleInPlaceActiveObject` zusätzlich zu `IOleDocumentView`:

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

Jede Ansicht verfügt über eine zugeordnete Ansicht-Website, die die Ansichtsframe und der Viewport (HWND und eines rechteckigen Bereichs, in diesem Fenster) kapselt. Die Website bietet diese Funktionalität jedoch den Standard `IOleInPlaceSite` Schnittstelle. Beachten Sie, dass es möglich ist, haben mehrere Viewport auf ein einzelnes HWND.

Jede Art von Ansicht wurde in der Regel eine andere gedruckte Darstellung. Daher Ansichten und die entsprechende Ansicht Standorte sollten die Drucken Schnittstellen implementieren Wenn `IPrint` und `IContinueCallback`bzw. Die Ansichtsframe muss mit dem ansichtsanbieter über aushandeln `IPrint` bei Beginn des Druckens, sodass Kopfzeilen, Fußzeilen, Seitenränder und verwandten Elementen ordnungsgemäß gedruckt werden. Benachrichtigt den Rahmen der Ereignisse in Zusammenhang mit der ansichtsanbieter `IContinueCallback`. Weitere Informationen zur Verwendung dieser Schnittstellen finden Sie unter [programmgesteuerten Drucken](../mfc/programmatic-printing.md).

Beachten Sie, wenn ein aktives Dokument nur eine einzigen Ansicht unterstützt, klicken Sie dann das aktive Dokument und die einzelne Ansicht implementiert werden können mit einer einzigen konkreten Klasse. `IOleDocument::CreateView` Gibt zurück, des gleichen Objekts einfach `IOleDocumentView` Schnittstellenzeiger auf. Kurz gesagt, ist es nicht erforderlich, die zwei separate Instanzen vorhanden sein, wenn nur eine Ansicht erforderlich ist.

Ein Objekt kann auch ein Befehlsziel sein. Durch die Implementierung `IOleCommandTarget` eine Sicht erhalten Befehle, die in der Benutzeroberfläche des Containers stammen (z. B. **neu**, **öffnen**, **speichern**,  **Drucken** auf die **Datei** Menü und **Kopie**, **einfügen**, **Rückgängig** auf die **Bearbeiten** Menü). Weitere Informationen finden Sie unter [Nachrichtenbehandlung und Befehlsziele](../mfc/message-handling-and-command-targets.md).

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containment.md)
