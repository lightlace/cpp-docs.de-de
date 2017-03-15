---
title: CDocItem Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
dev_langs:
- C++
helpviewer_keywords:
- items, document
- document items
- server documents, document items
- CDocItem class
- container document items
- client document items
- OLE documents, items
- server documents
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1ade88aa562180d5c3a6a7afe3fe26943a5d811d
ms.lasthandoff: 02/24/2017

---
# <a name="cdocitem-class"></a>CDocItem-Klasse
Die Basisklasse für Dokumentelemente, die Komponenten der Daten eines Dokuments sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|Gibt das Dokument zurück, das das Element enthält.|  
|[CDocItem::IsBlank](#isblank)|Bestimmt, ob das Element alle Informationen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 `CDocItem`Objekte werden verwendet, um OLE-Elemente in Client- und Dokumente darzustellen.  
  
 Weitere Informationen finden Sie im Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-namegetdocumenta--cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument  
 Rufen Sie diese Funktion, um das Dokument abzurufen, das das Element enthält.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL**, wenn das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist in den abgeleiteten Klassen überschrieben [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md), die Rückgabe eines Zeigers auf eine [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder ein [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Objekt.  
  
##  <a name="a-nameisblanka--cdocitemisblank"></a><a name="isblank"></a>CDocItem::IsBlank  
 Vom Framework aufgerufen, wenn Standardserialisierung auftritt.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element keine Informationen enthält; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CDocItem` Objekte sind nicht leer. [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekte sind manchmal leer, da sie direkte Ableitung `CDocItem`. Allerdings [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte sind immer leer. In der Standardeinstellung werden OLE-Programme, die mit `COleClientItem` Objekte, die keine x- oder y verfügen Block serialisiert werden. Dies erfolgt durch das Zurückgeben von **TRUE** von einer Überschreibung von `IsBlank` Wenn das Element verfügt über keine x oder y Block.  
  
 Überschreiben Sie diese Funktion, wenn Sie andere Aktionen während der Serialisierung implementieren möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)

