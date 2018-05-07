---
title: CDocItem Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e5017f51a3527e2ad81bcf707179053cc3e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdocitem-class"></a>CDocItem-Klasse
Die Basisklasse für Dokumentelemente, die Komponenten der Daten eines Dokuments sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|Gibt das Dokument, das das Element enthält.|  
|[CDocItem::IsBlank](#isblank)|Bestimmt, ob das Element alle Informationen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 `CDocItem` Objekte werden verwendet, um OLE-Elemente in Client- und Dokumente darzustellen.  
  
 Weitere Informationen finden Sie im Artikel [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="getdocument"></a>  CDocItem::GetDocument  
 Rufen Sie diese Funktion, um das Dokument zu erhalten, das das Element enthält.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL**, sofern das Element nicht Teil eines Dokuments ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in den abgeleiteten Klassen überschrieben [COleClientItem](../../mfc/reference/coleclientitem-class.md) und [COleServerItem](../../mfc/reference/coleserveritem-class.md), die Rückgabe eines Zeigers auf eine [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder ein [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Objekt.  
  
##  <a name="isblank"></a>  CDocItem::IsBlank  
 Vom Framework aufgerufen, wenn Standardserialisierung auftritt.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element keine Informationen enthält; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `CDocItem` Objekte sind nicht leer. [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekte sind in einigen Fällen leer, da sie direkte ableiten `CDocItem`. Allerdings [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte sind immer leer. In der Standardeinstellung werden OLE-serveranwendungen mit `COleClientItem` Objekte, die keine x- oder y verfügen Block serialisiert werden. Dies wird durch Zurückgeben von **"true"** von einer Überschreibung von `IsBlank` Wenn das Element besitzt, keine x- oder y Block.  
  
 Überschreiben Sie diese Funktion, wenn Sie andere Aktionen während der Serialisierung implementieren möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)
