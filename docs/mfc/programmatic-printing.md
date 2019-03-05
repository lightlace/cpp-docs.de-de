---
title: Programmgesteuertes Drucken
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
ms.openlocfilehash: eb8804610832f91f4b24487fddfe9c24a3799117
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264000"
---
# <a name="programmatic-printing"></a>Programmgesteuertes Drucken

OLE bereitgestellt, die Möglichkeit, persistente Dokumente eindeutig zu identifizieren (`GetClassFile`) und sie in der zugehörige Code laden (`CoCreateInstance`, `QueryInterface(IID_IPersistFile)`, `QueryInterface(IID_IPersistStorage)`, `IPersistFile::Load`, und `IPersistStorage::Load`). Zum Drucken von Dokumenten weiter zu aktivieren, führt active Document-Container (mit einem vorhandenen OLE-Entwurf, die nicht zum Funktionsumfang von OLE 2.0 ursprünglich) eine Basis-Standard-Druck-Schnittstelle, `IPrint`Allgemein verfügbaren über jedes Objekt, das Laden der persistente Zustand des Dokumenttyps. Jede Ansicht eines aktiven Dokuments kann optional unterstützen die `IPrint` Schnittstelle, um diese Funktionen bereitzustellen.

Die `IPrint` Schnittstelle wird wie folgt definiert:

```
interface IPrint : IUnknown
    {
    HRESULT SetInitialPageNum([in] LONG nFirstPage);
    HRESULT GetPageInfo(
        [out] LONG *pnFirstPage,
        [out] LONG *pcPages);
    HRESULT Print(
        [in] DWORD grfFlags,
        [in,out] DVTARGETDEVICE **pptd,
        [in,out] PAGESET ** ppPageSet,
        [in,out] STGMEDIUM **ppstgmOptions,
        [in] IContinueCallback* pCallback,
        [in] LONG nFirstPage,
        [out] LONG *pcPagesPrinted,
        [out] LONG *pnPageLast);
    };
```

-Clients und Container verwenden, die einfach `IPrint::Print` um anzuweisen, das Dokument selbst zu drucken, nach dem Laden dieses Dokuments angeben, Drucken Steuerungsflags, das Zielgerät, der zu druckenden, Seiten und zusätzlichen Optionen. Der Client kann auch steuern, die Fortsetzung des Druckens über die Schnittstelle `IContinueCallback` (siehe unten).

Darüber hinaus `IPrint::SetInitialPageNum` unterstützt die Möglichkeit, eine Reihe von Dokumenten von einem Nummerierung nahtlos, natürlich einen Vorteil für active Document-Container, z. B. Office Binder Seiten gedruckt werden. `IPrint::GetPageInfo` Anzeigen von einfachen Paginierungsinformationen ermöglicht dem aufrufenden ab, der abgerufen wird die zuvor bestandenen Nummer der Seite `SetInitialPageNum` (oder des Dokuments interne Standardthema zum Starten der Seitenzahl) und die Anzahl der Seiten im Dokument.

-Objekte zur Unterstützung `IPrint` in der Registrierung gekennzeichnet sind, die mit dem "Printable"-Schlüssel unter der CLSID des Objekts gespeichert:

HKEY_CLASSES_ROOT\CLSID\\{...}\Printable

`IPrint` wird in der Regel implementiert, für das gleiche Objekt, das entweder unterstützt `IPersistFile` oder `IPersistStorage`. Aufrufer beachten des persistenten Status einer bestimmten Klasse programmgesteuert zu drucken, indem Sie in der Registrierung für den Schlüssel "Printable" suchen. Derzeit "Druckbaren" gibt die Unterstützung für mindestens `IPrint`; andere Schnittstellen können definiert werden in Zukunft das wäre dann über `QueryInterface` , in denen `IPrint` steht einfach für das Basis-Maß an Unterstützung.

Bei einer Prozedur print sollten Sie den Client oder den Container, die initiiert das Drucken aus, um zu steuern, ob das Drucken fortgesetzt werden soll. Der Container kann z. B. einen Befehl "Beenden" Print "unterstützen, der den Druckauftrag so bald wie möglich beendet werden soll. Um diese Funktion zu unterstützen, kann der Client über ein druckbares-Objekt eine kleine Benachrichtigung Senkenobjekts mit der Schnittstelle implementieren `IContinueCallback`:

```
interface IContinueCallback : IUnknown
    {
    HRESULT FContinue(void);
    HRESULT FContinuePrinting(
        [in] LONG cPagesPrinted,
        [in] LONG nCurrentPage,
        [in] LPOLESTR pszPrintStatus);
    };
```

Diese Schnittstelle soll als eine generische Funktion nützlich sein, die der verschiedenen Fortsetzung Verfahren in der Win32-API stattfindet (z. B. die `AbortProc` für den Druck und `EnumMetafileProc` für Metafile-Enumeration). Daher eignet sich dieser Entwurf der Benutzeroberfläche in einer Vielzahl von zeitaufwändige Prozesse.

In den meisten generischen Fällen die `IContinueCallback::FContinue` Funktion wird in regelmäßigen Abständen von einem beliebigen langwierigen Prozess aufgerufen. Das Empfängerobjekt gibt S_OK zurück, um den Vorgang fortzusetzen, und S_FALSE, um das Verfahren so bald wie möglich zu beenden.

`FContinue`, ist jedoch nicht im Kontext des verwendet `IPrint::Print`, sondern Drucken verwendet `IContinueCallback::FContinuePrint`. Alle Druckobjekt sollten in regelmäßigen Abständen Aufrufen `FContinuePrinting` übergeben, die Anzahl der Seiten, die Druckobjekt, die Anzahl der zu druckenden Seite und einer zusätzlichen Zeichenfolge, die mit dem Druckstatus, die der Client auswählen kann, die der Benutzer (z. B. "-Seite angezeigt (5 von 19-Zoll).

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containers.md)
