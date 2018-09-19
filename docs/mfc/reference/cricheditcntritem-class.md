---
title: CRichEditCntrItem-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 17f50f5e4fb8b9330a09d4964aa99fbf01f4b34d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206970"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem-Klasse
Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-/ Ansichtarchitektur bereit.  
  
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
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Aktiviert das Element als einen anderen Typ.|  
  
## <a name="remarks"></a>Hinweise  
 Als "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text Zeichen- und absatzformatierung zugewiesen werden kann, und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die textformatierung an. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich, um Formatierungsvorgängen für den Benutzer verfügbar zu machen implementieren.  
  
 `CRichEditView` verwaltet den Text und Formatierung Merkmal des Texts. `CRichEditDoc` verwaltet die Liste der OLE-Clientelemente, in der Ansicht sind. `CRichEditCntrItem` Stellt die Container-Seite, auf das Client-OLE-Element.  
  
 Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandten Klassen) ist nur für Programme, die unter Versionen des Windows 95/98 und Windows NT 3.51 und höher.  
  
 Ein Beispiel der Verwendung von rich-Edit-Container-Elemente in einer MFC-Anwendung finden Sie unter den [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 Mit dieser Funktion wird zum Erstellen einer `CRichEditCntrItem` -Objekt und dem Container-Dokument hinzufügen.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *preo*  
 Zeiger auf ein [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Struktur, die ein OLE-Element beschreibt. Die neue `CRichEditCntrItem` Objekt wird erstellt, um diese OLE-Element. Wenn *Preo* NULL ist, die Client-Element ist leer.  
  
 *pContainer*  
 Zeiger auf das Containerdokument, das dieses Element enthält. Wenn *pContainer* NULL ist, müssen Sie explizit aufrufen [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) dieses Clientelement zu einem Dokument hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt keine OLE-Initialisierung aus.  
  
 Weitere Informationen finden Sie unter den [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Struktur im Windows SDK.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 Mit dieser Funktion können Sie den Aspekt Gerät synchronisieren [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), dieses `CRichEditCntrltem` , angegeben durch *Reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Parameter  
 *REO*  
 Ein Verweis auf ein [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Struktur, die ein OLE-Element beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
