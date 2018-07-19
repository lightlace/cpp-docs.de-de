---
title: Programmgesteuertes Drucken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbbc9792fcaec6713e13b4665568017bc5ce1bdc
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930926"
---
# <a name="programmatic-printing"></a>Programmgesteuertes Drucken
OLE bereitgestellt, die Mittel zur eindeutigen Identifizierung der persistente Dokumente (`GetClassFile`) und Laden Sie diese in den zugehörigen Code (`CoCreateInstance`, `QueryInterface(IID_IPersistFile)`, `QueryInterface(IID_IPersistStorage)`, `IPersistFile::Load`, und `IPersistStorage::Load`). Zum Drucken von Dokumenten weiter zu aktivieren, wird active Document-Container (über einen vorhandenen OLE-Entwurf, die ursprünglich nicht mit OLE 2.0 geliefert) eine Basis-Standard-drucken-Schnittstelle eingeführt, mit denen `IPrint`, die in der Regel über jedes Objekt, das geladen wird, kann die persistenten Status des Dokumenttyps. Jede Ansicht eines aktiven Dokuments kann optional unterstützen die `IPrint` Schnittstelle, um diese Funktionen bereitzustellen.  
  
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
  
 Clients und Container verwenden, die einfach `IPrint::Print` auf das Dokument anzuweisen, selbst wenn das Dokument drucken Steuerungsflags, dem Zielgerät, die geladen ist zu druckenden, Seiten angeben, Drucken und zusätzliche Optionen. Der Client kann auch steuern, die Fortsetzung des Druckens über die Schnittstelle `IContinueCallback` (siehe unten).  
  
 Darüber hinaus `IPrint::SetInitialPageNum` unterstützt die Fähigkeit, eine Reihe von Dokumenten zu drucken, wie von einem Nummerierung nahtlos offensichtlich einen Vorteil für active Document-Container wie Office Binder Seiten. `IPrint::GetPageInfo` Anzeigen von einfachen Paginierungsinformationen ermöglicht den Aufrufer zum Starten abgerufen wird die Seitenzahl zuvor bestandenen `SetInitialPageNum` (oder das Dokument interne Standardthema zum Starten der Seitenzahl) und die Anzahl der Seiten im Dokument.  
  
 -Objekte zur Unterstützung `IPrint` sind in der Registrierung mit der Sekundärschlüssel für "Printable" unter der CLSID des Objekts gekennzeichnet:  
  
 HKEY_CLASSES_ROOT\CLSID\\{...} \Printable  
  
 `IPrint` wird in der Regel implementiert, auf das gleiche Objekt, das entweder unterstützt `IPersistFile` oder `IPersistStorage`. Aufrufer Beachten Sie die Möglichkeit, persistenten Status einer Klasse programmgesteuert zu drucken, indem Sie in der Registrierung für den Schlüssel "Printable" suchen. Derzeit "Druckbaren" gibt die Unterstützung für mindestens `IPrint`; andere Schnittstellen möglicherweise definiert in der Zukunft der wäre dann erhältlich `QueryInterface` , in dem `IPrint` einfach stellt die Basis Maß an Unterstützung.  
  
 Während eines Drucken sollten Sie den Client oder den Container, die initiiert das Drucken, um zu steuern, ob das Drucken fortgesetzt werden soll. Der Container kann z. B. einen Befehl "Beenden" Print "unterstützen, der den Druckauftrag so bald wie möglich beendet werden soll. Zur Unterstützung dieser Funktion kann der Client über ein anderes druckbares Objekt implementieren eine kleine Benachrichtigungsobjekt des Senke mit der Schnittstelle `IContinueCallback`:  
  
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
  
 Diese Schnittstelle dient als eine generische Funktion nützlich sein, der die verschiedenen Fortsetzung Prozeduren in der Win32-API stattfindet (z. B. die `AbortProc` für den Druck und die `EnumMetafileProc` für Metadatei Enumeration). Daher eignet sich dieser Schnittstellenentwurf in einer Vielzahl von zeitaufwändigen Prozesse.  
  
 Im allgemeinsten Fall die `IContinueCallback::FContinue` Funktion wird in regelmäßigen Abständen von einem beliebigen langwierigen Prozess aufgerufen. Sink-Objekt gibt S_OK zurück, um den Vorgang fortzusetzen, und "S_FALSE", um das Verfahren so bald wie möglich zu beenden.  
  
 `FContinue`, jedoch nicht im Kontext des verwendet `IPrint::Print`, sondern Drucken verwendet `IContinueCallback::FContinuePrint`. Jedes Objekt Drucken sollten in regelmäßigen Abständen Aufrufen `FContinuePrinting` übergeben, die Anzahl der Seiten, die gedruckt haben, die Anzahl der gedruckten Seite und eine zusätzliche Zeichenfolge beschreibt den Status der Druckaufträge, die der Client auswählen kann, die der Benutzer (z. B. "Seite angezeigt 5 von 19").  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containers.md)

