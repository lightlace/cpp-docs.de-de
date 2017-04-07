---
title: CDocObjectServerItem Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServerItem class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
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
ms.openlocfilehash: 06cf873512fbf43b729d9a70f185582a4e48cafc
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem-Klasse
Implementiert OLE-Serververben speziell für DocObject-Server.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Erstellt ein `CDocObjectServerItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Ruft einen Zeiger auf das Dokument, das das Element enthält.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|Löst eine Ausnahme aus, wenn das Framework wird versucht, ein DocObject-Element auszublenden.|  
|[CDocObjectServerItem::OnShow](#onshow)|Aufgerufen, die DocObject Element direktes vornehmen aktiv. Wenn das Element nicht DocObject ist, ruft [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServerItem`überschreibbare Memberfunktionen definiert: [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), und [OnShow](#onshow).  
  
 Mit `CDocObjectServerItem`, sicherstellen, dass die [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) außer Kraft setzen, Ihrer `COleServerDoc`-abgeleiteten Klasse gibt eine neue `CDocObjectServerItem` Objekt. Wenn Sie alle Funktionen in Ihren Artikel ändern müssen, können Sie eine neue Instanz der eigene erstellen `CDocObjectServerItem`-abgeleiteten Klasse.  
  
 Weitere Informationen über DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem  
 Erstellt ein `CDocObjectServerItem`-Objekt.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 `pServerDoc`  
 Ein Zeiger auf das Dokument, das das neue DocObject-Element enthält.  
  
 `bAutoDelete`  
 Gibt an, ob das Objekt gelöscht werden kann, wenn ein Link freigegeben wird. Das Argument **FALSE** Wenn das `CDocObjectServerItem` Objekt ist ein integraler Bestandteil der Daten des Dokuments. Legen Sie es auf **TRUE** Wenn das Objekt eine sekundäre Struktur verwendet, um einen Bereich in die Daten des Dokuments zu identifizieren, die vom Framework gelöscht werden können.  
  
##  <a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 Ruft einen Zeiger auf das Dokument, das das Element enthält.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht den Zugriff auf die Server-Dokument, das Sie als Argument übergeben der [CDocObjectServerItem](#cdocobjectserveritem) Konstruktor.  
  
##  <a name="onhide"></a>CDocObjectServerItem::OnHide  
 Aufgerufen, um das Element auszublenden.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung löst eine Ausnahme aus, wenn das Element ein DocObject ist. Ein aktives DocObject-Element kann nicht ausgeblendet werden, da es die ganze Sicht akzeptiert. Sie müssen das DocObject-Element, um auszublenden, deaktivieren. Wenn das Element nicht DocObject ist, ruft die Implementierung der [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>CDocObjectServerItem::OnShow  
 Aufgerufen, um anzuweisen, die Serveranwendung, um die DocObject Element direktes, aktiv.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Element nicht DocObject ist, ruft die Implementierung der [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung beim Öffnen ein DocObject-Element ausführen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer-Klasse](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem-Klasse](../../mfc/reference/coledocobjectitem-class.md)

