---
title: CDocObjectServerItem-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e660144808c3e9abf8f8c090b9af5ff2eb73d9e9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211804"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem-Klasse
Implementiert OLE-Serververben speziell für DocObject-Server.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Erstellt ein `CDocObjectServerItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Ruft einen Zeiger auf das Dokument mit dem Element ab.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|Löst eine Ausnahme aus, wenn das Framework wird versucht, eine DocObject-Element auszublenden.|  
|[CDocObjectServerItem::OnShow](#onshow)|Aufgerufen, um das Objekt Element direktes machen aktiv. Wenn das Element nicht DocObject ist, ruft [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServerItem` überschreibbare Memberfunktionen definiert: [OnHide](#onhide), [OnOpen](https://msdn.microsoft.com/7a9b1363-6ad8-4732-9959-4e35c07644fd), und [OnShow](#onshow).  
  
 Verwendung von `CDocObjectServerItem`, stellen sicher, dass die [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) außer Kraft setzen, Ihre `COleServerDoc`-abgeleiteten Klasse gibt eine neue `CDocObjectServerItem` Objekt. Wenn Sie alle Funktionen in Ihren Artikel ändern müssen, können Sie erstellen eine neue Instanz Ihrer eigenen `CDocObjectServerItem`-abgeleitete Klasse.  
  
 Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in die *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [aktive Dokumente](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [Abgeleitete COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 Erstellt ein `CDocObjectServerItem`-Objekt.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parameter  
 *pServerDoc*  
 Ein Zeiger auf das Dokument, das das neue DocObject-Element enthält.  
  
 *bAutoDelete*  
 Gibt an, ob das Objekt gelöscht werden kann, wenn ein Link zu ihr freigegeben wird. Legen Sie das Argument FALSE, wenn die `CDocObjectServerItem` Objekt ist ein wesentlicher Bestandteil der Daten des Dokuments. Legen Sie sie auf "true", wenn das Objekt ist eine sekundäre Struktur verwendet, um einen Bereich in die Daten des Dokuments zu identifizieren, die vom Framework gelöscht werden kann.  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 Ruft einen Zeiger auf das Dokument mit dem Element ab.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; NULL, wenn das Element nicht Teil eines Dokuments ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht den Zugriff auf das Serverdokument, das Sie als Argument übergeben die [CDocObjectServerItem](#cdocobjectserveritem) Konstruktor.  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 Wird aufgerufen, durch das Framework, um das Element auszublenden.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung löst eine Ausnahme aus, wenn das Element DocObject ist. Ein aktives DocObject-Element kann nicht ausgeblendet werden, weil es dauert, die ganze Sicht wird. Sie müssen das DocObject-Element, um auszublenden deaktivieren. Wenn das Element nicht DocObject ist, ruft die standardmäßige Implementierung [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 Wird aufgerufen, durch das Framework angewiesen, den Serveranwendung, um das Objekt Element direktes, aktiv.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Element nicht DocObject ist, ruft die standardmäßige Implementierung [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung beim Öffnen ein DocObject-Element ausführen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer-Klasse](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem-Klasse](../../mfc/reference/coledocobjectitem-class.md)
