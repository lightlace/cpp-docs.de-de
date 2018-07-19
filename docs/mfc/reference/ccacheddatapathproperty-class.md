---
title: CCachedDataPathProperty-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: f0a3f632f2da327dea698722177ba6a3b3ebe42d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339786"
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
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` Objekt, in dem Daten zwischengespeichert werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Arbeitsspeicherdatei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert und eignet sich zur schnellen temporären Übertragungen.  
  
 Zusammen mit `CAysncMonikerFile` und `CDataPathProperty`, `CCachedDataPathProperty` stellt Funktionen für die Verwendung von asynchronen Monikern in OLE-Steuerelemente bereit. Mit `CCachedDataPathProperty` Objekte, können Sie asynchron übertragen von Daten aus einer URL-Zeichenfolge oder Quelle aus, und speichern es in einer Arbeitsspeicherdatei über die `m_Cache` öffentliche Variable. Alle Daten in der Speicherdatei gespeichert ist, und besteht keine Notwendigkeit zum Überschreiben [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) es sei denn, Sie möchten, sehen Sie sich für Benachrichtigungen und darauf reagieren. Beispielsweise wenn Sie eine große übertragen werden. GIF-Datei und möchten dem Steuerelement zu benachrichtigen, dass mehr Daten empfangen wurden, und es neu gezeichnet werden soll, überschreiben `OnDataAvailable` auf die Benachrichtigung gesendet haben.  
  
 Die Klasse `CCachedDataPathProperty` ergibt sich aus `CDataPathProperty`.  
  
 Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelementen in Internet-Anwendungen finden Sie unter den folgenden Themen:  
  
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
 *pControl*  
 Ein Zeiger auf das ActiveX-Steuerelement-Objekt zugeordnet sein `CCachedDataPathProperty` Objekt.  
  
 *lpszPath*  
 Der Pfad, der absolut oder relativ sein kann, verwendet, um die ein asynchrones Monikers zu erstellen, das die tatsächlichen absolute Position der Eigenschaft verweist. `CCachedDataPathProperty` verwendet nicht die Dateinamen-URLs. Wenn Sie möchten eine `CCachedDataPathProperty` Objekt für eine Datei, file:// auf den Pfad voranstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleControl` Objekt verweist *pControl* dient der [öffnen](../../mfc/reference/cdatapathproperty-class.md#open) und von abgeleiteten Klassen abgerufen. Wenn *pControl* NULL ist, das Steuerelement ab, mit `Open` sollten nastavit mit [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Wenn *LpszPath* NULL ist, können Sie den Pfad durch übergeben `Open` oder legen Sie sie mit [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 Enthält den Namen der Datei für den Speicher, die Sie in den Daten zwischengespeichert werden.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Arbeitsspeicherdatei wird im Arbeitsspeicher und nicht auf dem Datenträger gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty-Klasse](../../mfc/reference/cdatapathproperty-class.md)
