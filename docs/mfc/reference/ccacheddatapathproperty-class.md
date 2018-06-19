---
title: CCachedDataPathProperty Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29e46f7e65d6c2f9b5c0d29007cd31f660754957
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355459"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty-Klasse
Implementiert eine asynchron übertragene und in einer Arbeitsspeicherdatei zwischengespeicherte OLE-Steuerelementeigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Erstellt ein `CCachedDataPathProperty`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` Objekt in der zum Zwischenspeichern von Daten.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Arbeitsspeicherdatei wird im Arbeitsspeicher und nicht auf dem Datenträger gespeichert und eignet sich für schnelle temporäre Übertragungen.  
  
 Zusammen mit **CAysncMonikerFile** und `CDataPathProperty`, `CCachedDataPathProperty` bietet Funktionen für die Verwendung von asynchronen Monikern in OLE-Steuerelemente. Mit `CCachedDataPathProperty` Objekte können Sie Daten aus einer Quelle URL- oder asynchron übertragen und speichern Sie sie in einer Arbeitsspeicherdatei über die `m_Cache` öffentliche Variable. Alle Daten in der Speicherdatei gespeichert ist, und besteht keine Notwendigkeit, überschreiben [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) es sei denn, Sie verwenden möchten, sehen Sie sich für Benachrichtigungen und reagieren. Beispielsweise, wenn Sie eine große übertragen werden. GIF-Datei und möchten dem Steuerelement zu benachrichtigen, dass mehr Daten empfangen wurden, und es sollte, die selbst neu zeichnet überschreiben `OnDataAvailable` die Benachrichtigung vornehmen.  
  
 Die Klasse `CCachedDataPathProperty` stammt aus `CDataPathProperty`.  
  
 Weitere Informationen zum Verwenden von asynchronen Monikern und ActiveX-Steuerelemente im Internet-Anwendungen finden Sie unter den folgenden Themen:  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty  
 Erstellt ein `CCachedDataPathProperty`-Objekt.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf das ActiveX-Steuerelementobjekt mit diesem verbunden sein, `CCachedDataPathProperty` Objekt.  
  
 `lpszPath`  
 Der Pfad absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die eigentliche absolute Position der Eigenschaft verweist. `CCachedDataPathProperty` URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CCachedDataPathProperty` -Objekt für eine Datei, file:// auf den Pfad voranstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleControl` Objekt verweist `pControl` dient der [öffnen](../../mfc/reference/cdatapathproperty-class.md#open) und abgeleitete Klassen abgerufen. Wenn `pControl` ist **NULL**, das Steuerelement mit verwendet **öffnen** sollte festgelegt werden, mit [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Wenn `lpszPath` ist **NULL**, können Sie den Pfad durch übergeben **öffnen** oder legen Sie sie mit [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 Enthält den Klassennamen die Arbeitsspeicher-Datei in die Daten zwischengespeichert werden.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei wird im Arbeitsspeicher und nicht auf dem Datenträger gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)
