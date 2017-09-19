---
title: CRichEditDoc-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc-Klasse
Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der Dokument-/Ansichtarchitektur von MFC bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Wird aufgerufen, um die Bereinigung des Dokuments durchzuführen.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Gibt an, ob Stream Eingabe und Ausgabe Formatierungsinformationen enthalten soll.|  
|[CRichEditDoc::GetView](#getview)|Ruft den Zeilenindex [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Gibt an, ob e/a-Stream Formatierung enthalten soll.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text zugewiesen werden kann, Zeichen- und absatzformatierung und eingebettete OLE-Objekte enthalten kann. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle zum Formatieren von Text. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich Formatierungsvorgängen der Benutzer zur Verfügung stellen implementieren.  
  
 `CRichEditView`der Text und Formatierung Texteigenschaft beibehalten. `CRichEditDoc`verwaltet die Liste der Clientelemente, die angezeigt wird. `CRichEditCntrItem`Container-Seite Zugriff auf die OLE-Clientelemente.  
  
 Diese Windows-Standardsteuerelement (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandte Klassen) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Ein Beispiel für ein rich-Edit-Dokument in einer MFC-Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) -Beispiel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Rufen Sie diese Funktion zum Erstellen einer `CRichEditCntrItem` -Objekt und fügen sie zu diesem Dokument.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 *preo*  
 Zeiger auf eine [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Struktur, die ein OLE-Element beschreibt. Die neue `CRichEditCntrItem` -Objekt wird erstellt, um diese OLE-Element. Wenn *Preo* ist **NULL**, das neue Clientelement ist leer.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein neues [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt, das zu diesem Dokument hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt keine OLE-Initialisierung.  
  
 Weitere Informationen finden Sie unter der [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Rufen Sie diese Funktion, um zu bestimmen, das Text-Format für den Inhalt des rich-Edit streaming.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- `SF_TEXT`Gibt an, dass das rich-Edit-Steuerelement nicht Formatierung beibehält.  
  
- `SF_RTF`Gibt an, dass das rich-Edit-Steuerelement Informationen über die Formatierung beibehält.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert basiert auf der [M_bRTF](#m_brtf) -Datenmember. Diese Funktion gibt `SF_RTF` Wenn `m_bRTF` ist **TRUE**, andernfalls `SF_TEXT`.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 Rufen Sie diese Funktion für den Zugriff auf die [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt zugeordneten `CRichEditDoc` Objekt.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die `CRichEditView` Objekt, das mit dem Dokument zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Text und Formatierung Informationen enthalten sind die `CRichEditView` Objekt. Das `CRichEditDoc` -Objekt verwaltet die OLE-Elemente für die Serialisierung. Sollte es nicht nur eine `CRichEditView` für jede `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Wenn **TRUE**, gibt an, dass [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) und [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) sollten Absatz- und Zeichenformaten Merkmale speichern.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl-Klasse](../../mfc/reference/cricheditctrl-class.md)

