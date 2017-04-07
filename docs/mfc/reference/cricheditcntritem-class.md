---
title: CRichEditCntrItem Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem class
- OLE items, in rich edit views
- rich edit controls, using
- rich edit controls, OLE items
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
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
ms.openlocfilehash: b29c7c3b80d24ef9ddb94e09c6b5c7bf2444bb4f
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem-Klasse
Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der Dokument-/Ansichtarchitektur von MFC bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Erstellt ein `CRichEditCntrItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Aktiviert das Element als anderer Typ.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text zugewiesen werden kann, Zeichen- und absatzformatierung und eingebettete OLE-Objekte enthalten kann. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle zum Formatieren von Text. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich Formatierungsvorgängen der Benutzer zur Verfügung stellen implementieren.  
  
 `CRichEditView`der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc`verwaltet die Liste der OLE-Client-Elemente, die in der Ansicht sind. `CRichEditCntrItem`Container-Seite Zugriff auf das Client-OLE-Element.  
  
 Diese Windows-Standardsteuerelement (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel für rich-Edit-Container-Elemente in einer MFC-Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) -Beispiel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem  
 Rufen Sie diese Funktion zum Erstellen einer `CRichEditCntrItem` -Objekt und das Containerdokument hinzuzufügen.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *preo*  
 Zeiger auf eine [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur, die ein OLE-Element beschreibt. Die neue `CRichEditCntrItem` -Objekt wird erstellt, um diese OLE-Element. Wenn *Preo* ist **NULL**, Client-Element ist leer.  
  
 `pContainer`  
 Ein Zeiger auf das Containerdokument, das dieses Element enthält. Wenn `pContainer` ist **NULL**, müssen Sie explizit aufrufen [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) ein Dokument dieses Clientelement hinzu.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt keine OLE-Initialisierung.  
  
 Weitere Informationen finden Sie unter der [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="synctoricheditobject"></a>CRichEditCntrItem::SyncToRichEditObject  
 Rufen Sie diese Funktion zum Synchronisieren des Aspekts Gerät [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), dieses **CRichEditCntrltem** , angegeben durch *Reo*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Parameter  
 *Musikvideo*  
 Ein Verweis auf eine [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur, die ein OLE-Element beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)

