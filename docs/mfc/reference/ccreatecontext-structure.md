---
title: CCreateContext-Struktur
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: f84c0da7530a774ebe2b33aea0bddc5b0bf0fe17
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326347"
---
# <a name="ccreatecontext-structure"></a>CCreateContext-Struktur

Das Framework verwendet die `CCreateContext` Struktur, wenn erstellt die Rahmenfenstern und Ansichten, die einem Dokument zugeordnet sind.

## <a name="syntax"></a>Syntax

```
struct CCreateContext
```

## <a name="remarks"></a>Hinweise

`CCreateContext` ist eine Struktur, und verfügt nicht über eine Basisklasse.

Wenn Sie ein Fenster erstellen, geben Sie die Werte in dieser Struktur der Informationen verwendet, um die Komponenten eines Dokuments an die Ansicht der Daten zu verbinden. Müssen Sie nur mit `CCreateContext` Wenn Sie Teile des Prozesses der außer Kraft gesetzt werden.

Ein `CCreateContext` Struktur enthält Verweise auf das Dokument, das Rahmenfenster, das Anzeigen und die Dokumentvorlage. Es enthält auch einen Zeiger auf eine `CRuntimeClass` , die den Typ des zu erstellenden Ansicht identifiziert. Die Laufzeit-Klasseninformationen und Zeiger für den aktuellen Dokument werden verwendet, um eine neue Ansicht dynamisch zu erstellen. Die folgende Tabelle enthält, wie und wann jedes `CCreateContext` Member verwendet werden kann:

|Member|Typ|Worum handelt es sich für|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` der neue Ansicht erstellen.|
|`m_pCurrentDoc`|`CDocument*`|Das vorhandene Dokument, das die neue Ansicht zugeordnet werden soll.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Die Dokumentvorlage, die die Erstellung einer neuen MDI-Rahmenfenster zugeordnet wird.|
|`m_pLastView`|`CView*`|Die ursprüngliche Ansicht, die für die zusätzliche Ansichten, wie die Erstellung von Ansichten der Splitter-Fenster oder die Erstellung einer zweiten Ansicht in einem Dokument modelliert werden.|
|`m_pCurrentFrame`|`CFrameWnd*`|Das Rahmenfenster, das für das zusätzliche Rahmenfenster, wie die Erstellung von ein zweites Rahmenfenster in einem Dokument modelliert werden.|

Wenn ein Dokument und die zugehörigen Komponenten eine Dokumentvorlage erstellt wird, überprüft er den Informationen in den `CCreateContext` Struktur. Beispielsweise sollte eine Ansicht für eine nicht vorhandene Dokument nicht erstellt werden.

> [!NOTE]
>  Der Zeiger in allen `CCreateContext` sind optional und kann `NULL` Wenn nicht angegeben oder unbekannt.

`CCreateContext` wird verwendet, durch die Member-Funktionen aufgeführt, die unter "Siehe auch". Finden Sie spezifische Informationen in die Beschreibungen dieser Funktionen, wenn Sie sie überschreiben möchten.

Hier sind einige allgemeine Richtlinien:

- Beim Übergeben als Argument für die fenstererstellung, wie in `CWnd::Create`, `CFrameWnd::Create`, und `CFrameWnd::LoadFrame`, den erstellen-Kontext angibt, was im neue Fenster mit verbunden werden sollen. Für die meisten Fenster, die gesamte Struktur ist optional und `NULL` Zeiger übergeben werden kann.

- Für überschreibbare Memberfunktionen z. B. `CFrameWnd::OnCreateClient`, `CCreateContext` Argument ist optional.

- Für Memberfunktionen Beteiligten müssen in der Ansicht erstellen, Sie genügend Informationen zum Erstellen der Ansicht angeben. Beispielsweise müssen Sie für die erste Ansicht in einem Splitterfenster, die Informationen des Ansicht-Klasse und das aktuelle Dokument angeben.

Im Allgemeinen, wenn Sie die Framework-Standards verwenden, können Sie ignorieren `CCreateContext`. Wenn Sie, erweiterte Änderungen, die Microsoft Foundation Class Library-Quellcode oder Beispielprogramme, z. B. VIEWEX versuchen, führt Sie. Wenn Sie einen erforderlichen Parameter vergisst, informiert eine Assertion Framework Sie, was haben Sie vergessen.

Weitere Informationen zu `CCreateContext`, finden Sie im MFC-Beispiel [VIEWEX](../../visual-cpp-samples.md).

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
