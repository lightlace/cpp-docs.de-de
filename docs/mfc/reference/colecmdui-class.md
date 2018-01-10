---
title: COleCmdUI Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs: C++
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9d26ce9e674168f3d3d1c67dc48bb16b1a87169
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="colecmdui-class"></a>COleCmdUI-Klasse
Implementiert eine Methode, die es MFC ermöglicht, den Zustand von Benutzeroberflächenobjekten zu aktualisieren, die in Bezug zu den `IOleCommandTarget`-gesteuerten Funktionen der Anwendung stehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Erstellt ein `COleCmdUI`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Aktiviert oder deaktiviert die Befehlsflag aktivieren.|  
|[COleCmdUI::SetCheck](#setcheck)|Legt den Status einer Umschaltfläche ein-oder auszuschalten Befehl.|  
|[COleCmdUI::SetText](#settext)|Gibt eine Textzeichenfolge Name oder Status für einen Befehl zurück.|  
  
## <a name="remarks"></a>Hinweise  
 In einer Anwendung, die für DocObjects, nicht aktiviert ist, wenn der Benutzer ein Menü in der Anwendung, die MFC-Prozesse anzeigt **UPDATE_COMMAND_UI** Benachrichtigungen. Jede Benachrichtigung erhält eine [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt, das bearbeitet werden kann, um den Status eines bestimmten Befehls widerspiegelt. Jedoch, wenn Ihre Anwendung für DocObjects aktiviert ist, MFC verarbeitet **UPDATE_OLE_COMMAND_UI** Benachrichtigungen und weist ihm `COleCmdUI` Objekte.  
  
 `COleCmdUI`kann DocObject um Befehle zu empfangen, die in den Container-Benutzeroberfläche (z. B. FileNew, öffnen, drucken usw.) stammen, und einen Container, um Befehle zu empfangen, die in der Benutzeroberfläche der DocObject stammen. Obwohl `IDispatch` kann verwendet werden, um die gleichen Befehle dispatch `IOleCommandTarget` bietet eine einfachere Möglichkeit zum Abfragen und ausgeführt werden, da es auf einen Standardsatz von Befehlen, die in der Regel ohne Argumente beruht und keine Typinformationen beteiligt ist. `COleCmdUI`kann verwendet werden, zum Aktivieren, aktualisieren und andere Eigenschaften des DocObject Benutzeroberflächenbefehlen festzulegen. Wenn Sie den Befehl aufrufen möchten, rufen Sie [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [aktive Dokumente](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocobj.h  
  
##  <a name="colecmdui"></a>COleCmdUI::COleCmdUI  
 Erstellt ein `COleCmdUI` Objekt, das mit einem bestimmten Benutzeroberflächen-Befehl zugeordnet.  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>Parameter  
 `rgCmds`  
 Eine Liste der unterstützten Befehle, die die angegebene GUID zugeordnet. Die **OLECMD** Struktur Befehlsflags Befehle zugeordnet.  
  
 *cCmds*  
 Die Anzahl der Befehle in `rgCmds`.  
  
 `pGroup`  
 Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleCmdUI` -Objekt stellt eine programmgesteuerte Schnittstelle für das Aktualisieren von Benutzeroberflächenobjekten DocObject z. B. Steuerleiste Schaltflächen oder Menüelemente bereit. Die Benutzeroberflächenobjekten können aktiviert, deaktiviert, überprüft und/oder werden deaktiviert, bis die `COleCmdUI` Objekt.  
  
##  <a name="enable"></a>COleCmdUI::Enable  
 Mit dieser Funktion wird zum Festlegen der Befehlsflag von der `COleCmdUI` -Objekt **OLECOMDF_ENABLED**, verfügbar und aktiviert ist, ist den Befehl weist der Schnittstelle oder die Kennzeichnung des Befehls zu löschen.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 Gibt an, ob die zugeordnete der Befehl die `COleCmdUI` Objekt aktiviert oder deaktiviert werden soll. Nonzero ermöglicht den Befehl. 0 deaktiviert den Befehl.  
  
##  <a name="setcheck"></a>COleCmdUI::SetCheck  
 Mit dieser Funktion wird zum Festlegen des Status einer Umschaltfläche ein-oder auszuschalten Befehl.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Ermitteln des Status einer Umschaltfläche ein-oder auszuschalten festzulegende Wert Befehl. Gültige Werte:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**1**|Der Befehl festgelegt auf on.|  
|**2**|Mit dem Befehl festgelegt einem unbestimmten Zustand; der Status kann nicht bestimmt werden, da das Attribut mit diesem Befehl sowohl auf und deaktiviert den Status in die entsprechende Auswahl wird.|  
|Ein anderer Wert|Mit dem Befehl auf off festgelegt.|  
  
##  <a name="settext"></a>COleCmdUI::SetText  
 Mit dieser Funktion wird zum Zurückgeben einer Textzeichenfolge Name oder Status für einen Befehl.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Ein Zeiger auf den Text, mit dem Befehl verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



