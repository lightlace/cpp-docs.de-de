---
title: CRichEditCntrItem Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0b4c038389810fcc6a847cdbf7837568b3007b6
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078607"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem-Klasse
Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-Ansichtsarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Erstellt ein `CRichEditCntrItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Aktiviert das Element als anderer Typ.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer eingeben kann, und Bearbeiten von Text. Der Text kann Zeichen- und absatzformatierung zugewiesen werden und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die Formatierung von Text an. Komponenten der Benutzeroberfläche zum Formatierungsvorgänge für den Benutzer verfügbar machen muss jedoch eine Anwendung implementiert werden.  
  
 `CRichEditView` der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc` verwaltet die Liste der OLE-Clientelemente, die in der Ansicht sind. `CRichEditCntrItem` OLE-Clientelement erläutert Container-Seite.  
  
 Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel der Verwendung von rich-Edit-Container-Elemente in einer MFC-Anwendung finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 Mit dieser Funktion wird zum Erstellen einer `CRichEditCntrItem` -Objekt und fügen es Containerdokument hinzu.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *preo*  
 Zeiger auf eine [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur der OLE-Element beschrieben wird. Die neue `CRichEditCntrItem` -Objekt erstellt wird, um diese OLE-Element. Wenn *Preo* ist **NULL**, Client-Element ist leer.  
  
 *pContainer*  
 Ein Zeiger auf die Containerdokument, das dieses Element enthält. Wenn *pContainer* ist **NULL**, müssen Sie explizit aufrufen [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) ein Dokument dieses Clientelement hinzu.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt keine OLE-Initialisierung.  
  
 Weitere Informationen finden Sie unter der [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur im Windows SDK.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 Mit dieser Funktion wird zum Synchronisieren des Aspekts Gerät [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), dieses `CRichEditCntrltem` , angegeben durch *Reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Parameter  
 *REO*  
 Ein Verweis auf ein [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur der OLE-Element beschrieben wird.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
