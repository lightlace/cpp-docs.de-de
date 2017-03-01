---
title: CCachedDataPathProperty Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- CCachedDataPathProperty class
- OLE controls [C++], asynchronous
- asynchronous controls [C++]
- memory files [C++]
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
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
ms.openlocfilehash: 6e3f54e6429456be24cbe18471abd1705bbe0034
ms.lasthandoff: 02/24/2017

---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty-Klasse
Implementiert eine asynchron übertragene und in einer Arbeitsspeicherdatei zwischengespeicherte OLE-Steuerelementeigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Erstellt ein `CCachedDataPathProperty`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`Objekt, in dem Daten zwischengespeichert werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert wird und eignet sich für schnelle temporäre übertragen.  
  
 Zusammen mit **CAysncMonikerFile** und `CDataPathProperty`, `CCachedDataPathProperty` bietet Funktionen für die Verwendung von asynchronen Monikern in OLE-Steuerelemente. Mit `CCachedDataPathProperty` Objekte können Sie Daten asynchron von einer URL oder Quelle übertragen und speichern es in eine Datei über die `m_Cache` öffentliche Variable. Alle Daten in der Speicherdatei gespeichert ist, und besteht keine Notwendigkeit zum Überschreiben [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) , wenn Sie Benachrichtigungen und reagieren möchten. Beispielsweise, wenn Sie eine große übertragen werden. GIF-Datei und möchten, dass dem Steuerelement zu benachrichtigen, dass mehr Daten empfangen wurden, und es neu gezeichnet werden soll, außer Kraft setzen `OnDataAvailable` auf die Benachrichtigung.  
  
 Die Klasse `CCachedDataPathProperty` abgeleitet ist `CDataPathProperty`.  
  
 Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelemente im Internet Applications finden Sie unter den folgenden Themen:  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="a-nameccacheddatapathpropertya--ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty  
 Erstellt ein `CCachedDataPathProperty`-Objekt.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf das ActiveX-Steuerelementobjekt zugeordnet sein `CCachedDataPathProperty` Objekt.  
  
 `lpszPath`  
 Der Pfad, der absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die tatsächliche absolute Position der Eigenschaft verweist. `CCachedDataPathProperty`URLs, keine Dateinamen verwendet. Wenn Sie möchten ein `CCachedDataPathProperty` -Objekt für eine Datei und file:// auf den Pfad voranstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleControl` Objekt verweist `pControl` werden [öffnen](../../mfc/reference/cdatapathproperty-class.md#open) und von abgeleiteten Klassen abgerufen. Wenn `pControl` ist **NULL**, das Steuerelement mit **öffnen** sollte festgelegt werden, mit [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Wenn `lpszPath` ist **NULL**, können Sie den Pfad durch übergeben **öffnen** oder legen Sie sie mit [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="a-namemcachea--ccacheddatapathpropertymcache"></a><a name="m_cache"></a>CCachedDataPathProperty::m_Cache  
 Enthält den Namen der Datei für den Speicher in den Daten zwischengespeichert werden.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei wird im Arbeitsspeicher und nicht auf dem Datenträger gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)

