---
title: Angegeben ist und Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af6e81b9215aa6e7bc9e5f294a1d95aee4b51321
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352043"
---
# <a name="ccreatecontext-structure"></a>Angegeben ist und-Struktur
Das Framework verwendet die `CCreateContext` Struktur beim Erstellen der Rahmenfenster und Ansichten, die mit einem Dokument verknüpft sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Hinweise  
 `CCreateContext` ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Wenn Sie ein Fenster erstellen, geben Sie die Werte in dieser Struktur der Informationen verwendet, um die Komponenten eines Dokuments zur Ansicht ihrer Daten zu verbinden. Sie müssen nur verwenden `CCreateContext` Wenn Teile des Erstellungsprozesses außer Kraft gesetzt werden.  
  
 Ein `CCreateContext` Struktur enthält Zeiger auf das Dokument, das Rahmenfenster, Ansicht und die Dokumentvorlage. Es enthält auch einen Zeiger auf eine `CRuntimeClass` , identifiziert den Typ des zu erstellenden Ansicht. Die Laufzeit Klasseninformationen und Zeiger auf den aktuellen Dokument werden verwendet, um eine neue Ansicht dynamisch zu erstellen. Die folgende Tabelle enthält, wie und wann jedes `CCreateContext` Member verwendet werden kann:  
  
|Member|Typ|Worum handelt es sich, für|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` der neue Sicht erstellen.|  
|`m_pCurrentDoc`|`CDocument*`|Zum vorhandenen Dokument an die neue Sicht zugeordnet werden soll.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Die Dokumentvorlage, die die Erstellung einer neuen MDI-Rahmenfenster zugeordnet.|  
|`m_pLastView`|`CView*`|Die ursprüngliche Ansicht auf die zusätzliche Ansichten, wie bei der Erstellung der Splitter Fensteransichten oder die Erstellung einer zweiten Ansicht eines Dokuments modelliert werden.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Das Rahmenfenster für das zusätzliche Rahmenfenster, wie die Erstellung von ein zweites Rahmenfenster in einem Dokument modelliert werden.|  
  
 Wenn eine Dokumentvorlage eines Dokuments und die zugehörigen Komponenten erstellt, überprüft Sie den Informationen in den `CCreateContext` Struktur. Beispielsweise sollte eine Sicht für eine nicht vorhandene Dokument nicht erstellt werden.  
  
> [!NOTE]
>  Alle Zeiger in `CCreateContext` sind optional und kann `NULL` Wenn nicht angegeben oder unbekannt.  
  
 `CCreateContext` wird verwendet, durch die Memberfunktionen aufgeführt, die unter "Siehe auch." Finden Sie in der Beschreibung dieser Funktionen finden Sie spezifische Informationen, wenn Sie planen, um sie zu überschreiben.  
  
 Es folgen einige allgemeine Richtlinien:  
  
-   Beim Übergeben als Argument für das Fenster erstellen, wie in `CWnd::Create`, `CFrameWnd::Create`, und `CFrameWnd::LoadFrame`, der erstellen-Kontext gibt an, was im neue Fenster mit verbunden werden sollen. Die gesamte Struktur für die meisten Windows ist optional und eine `NULL` Zeiger übergeben werden kann.  
  
-   Bei überschreibbare Memberfunktionen z. B. `CFrameWnd::OnCreateClient`die `CCreateContext` Argument ist optional.  
  
-   Für Memberfunktionen Beteiligten müssen in der Sicht erstellen, Sie genügend Informationen zum Erstellen der Ansicht bereitstellen. Beispielsweise müssen Sie für die erste Ansicht in einem Splitterfenster, die Informationen anzeigen und das aktuelle Dokument angeben.  
  
 Im Allgemeinen, wenn Sie die Standardwerte Framework verwenden, können Sie ignorieren `CCreateContext`. Wenn Sie, weitere Änderungen, die Microsoft Foundation Class Library-Quellcode oder die Beispielprogramme, z. B. VIEWEX versuchen, führt Sie. Wenn Sie einen erforderlichen Parameter vergessen, wird eine Assertion Framework Aufschluss darüber, haben Sie vergessen.  
  
 Weitere Informationen zu `CCreateContext`, finden Sie im MFC-Beispiel [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [Splitterfenstern](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd:: CreateView-Funktion](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)

