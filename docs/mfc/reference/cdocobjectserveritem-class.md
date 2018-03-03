---
title: CDocObjectServerItem Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7627fbc7cb5d36bd82e130264d2653d5a8464545
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CDocObjectServerItem::OnShow](#onshow)|Wird aufgerufen, durch das Framework der DocObject Element direktes vornehmen aktiv. Wenn das Element nicht DocObject ist, ruft [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServerItem`überschreibbare Memberfunktionen definiert: [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), und [OnShow](#onshow).  
  
 Mit `CDocObjectServerItem`, stellen sicher, dass die [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) außer Kraft setzen Ihre `COleServerDoc`-abgeleiteten Klasse gibt eine neue `CDocObjectServerItem` Objekt. Wenn Sie alle Funktionen in Ihren Artikel ändern müssen, können Sie eine neue Instanz der eigene erstellen `CDocObjectServerItem`-Klasse.  
  
 Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [aktive Dokumente](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ein Zeiger auf das Dokument, das das neue DocObject-Element enthalten soll.  
  
 `bAutoDelete`  
 Gibt an, ob das Objekt gelöscht werden kann, wenn ein Link zu ihr losgelassen wird. Legen Sie das Argument zu **"false"** Wenn die `CDocObjectServerItem` Objekt ist ein wesentlicher Bestandteil des Dokuments Daten. Legen Sie es auf **"true"** , wenn das Objekt ist eine sekundäre Struktur verwendet, um einen Bereich in Ihr Dokument Daten zu identifizieren, die vom Framework gelöscht werden kann.  
  
##  <a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 Ruft einen Zeiger auf das Dokument mit dem Element ab.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das das Element enthält; **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht den Zugriff auf das Serverdokument, das Sie als Argument zu übergeben der [CDocObjectServerItem](#cdocobjectserveritem) Konstruktor.  
  
##  <a name="onhide"></a>CDocObjectServerItem::OnHide  
 Wird aufgerufen, durch das Framework, um das Element auszublenden.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung löst eine Ausnahme aus, wenn das Element ein DocObject ist. Ein aktives DocObject-Element kann nicht ausgeblendet werden, weil er die ganze Sicht erhält. Das DocObject-Element, damit nicht mehr angezeigt werden können, muss deaktiviert werden. Wenn das Element nicht DocObject ist, ruft die standardmäßige Implementierung [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>CDocObjectServerItem::OnShow  
 Wird aufgerufen, durch das Framework um anzuweisen, die Serveranwendung die DocObject Element direktes stellen aktiv.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Element nicht DocObject ist, ruft die standardmäßige Implementierung [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung beim Öffnen einer DocObject-Element ausführen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer-Klasse](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem-Klasse](../../mfc/reference/coledocobjectitem-class.md)
