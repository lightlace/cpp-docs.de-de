---
title: Angegeben ist und Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
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
ms.openlocfilehash: 231f2e44e085d27a2b2cbf289adf7b0521471b0e
ms.lasthandoff: 02/24/2017

---
# <a name="ccreatecontext-structure"></a>Angegeben ist und Struktur
Das Framework verwendet die `CCreateContext` Struktur, wenn erstellt die Rahmenfenster und Ansichten, die einem Dokument zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Hinweise  
 `CCreateContext`ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Wenn Sie ein Fenster erstellen, geben Sie die Werte in dieser Struktur der Informationen verwendet, um die Komponenten eines Dokuments zur Ansicht der Daten zu verbinden. Sie müssen nur verwenden `CCreateContext` Wenn Sie Teile des Erstellungsprozesses außer Kraft gesetzt werden.  
  
 Ein `CCreateContext` Struktur enthält Verweise auf das Dokument, das Rahmenfenster, die Ansicht und die Dokumentvorlage aus. Es enthält auch einen Zeiger auf eine `CRuntimeClass` , identifiziert den Typ der zu erstellenden Ansicht. Die Laufzeit-Klasseninformationen und Zeiger auf den aktuellen Dokument werden verwendet, um eine neue Ansicht dynamisch zu erstellen. Die folgende Tabelle schlägt vor, wie und wann jeder `CCreateContext` Member verwendet werden kann:  
  
|Member|Typ|Worum handelt es sich für|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`der neue Ansicht erstellen.|  
|`m_pCurrentDoc`|`CDocument*`|Das bestehende Dokument die neue Ansicht zugeordnet werden soll.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Die Dokumentvorlage, die die Erstellung eines neuen MDI-Rahmenfensters zugeordnet.|  
|`m_pLastView`|`CView*`|Die ursprüngliche Ansicht, auf der zusätzliche Ansichten, wie der Splitter Fensteransichten zu erstellen oder die Erstellung einer zweiten Ansicht in einem Dokument modelliert werden.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Das Rahmenfenster, auf dem zusätzliche Rahmenfenster, wie die Erstellung eines zweiten Rahmenfensters für ein Dokument modelliert werden.|  
  
 Wenn eine Dokumentvorlage ein Dokument und den zugehörigen Komponenten erstellt, überprüft Sie den Informationen in der `CCreateContext` Struktur. Beispielsweise sollte eine Ansicht für ein nicht vorhandenes Dokument nicht erstellt werden.  
  
> [!NOTE]
>  Alle Zeiger in `CCreateContext` sind optional und kann `NULL` nicht festgelegt oder unbekannt.  
  
 `CCreateContext`werden die Memberfunktionen aufgeführt, unter "Siehe auch". Informationen finden Sie in der Beschreibung dieser Funktionen bestimmte überschrieben werden soll.  
  
 Hier sind einige allgemeine Richtlinien:  
  
-   Beim Übergeben als Argument für die fenstererstellung, wie in `CWnd::Create`, `CFrameWnd::Create`, und `CFrameWnd::LoadFrame`, der erstellen-Kontext gibt an, was das neue Fenster mit verbunden werden sollen. Für die meisten Windows die gesamte Struktur ist optional und einem `NULL` Zeiger übergeben werden kann.  
  
-   Für überschreibbare Memberfunktionen z. B. `CFrameWnd::OnCreateClient`der `CCreateContext` Argument ist optional.  
  
-   Für die Beteiligten Memberfunktionen in der Ansicht erstellen, genügend Informationen zum Erstellen der Ansicht benötigt. Beispielsweise müssen Sie für die erste Ansicht in einem Teilfenster, die Informationen anzeigen und das aktuelle Dokument angeben.  
  
 Im Allgemeinen, wenn Sie die Framework-Standards verwenden, können Sie ignorieren `CCreateContext`. Wenn Sie, weitere Änderungen, die Microsoft Foundation Class Library-Quellcode oder Beispielprogramme, z. B. die Wahl versuchen, führt Sie. Wenn Sie einen erforderlichen Parameter vergessen, informiert eine Assertion Framework Sie Sie vergessen haben.  
  
 Weitere Informationen zu `CCreateContext`, finden Sie im MFC-Beispiel [Wahl](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [Splitterfenstern](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd:: CreateView-Funktion](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd:: Create](../../mfc/reference/cwnd-class.md#create)


