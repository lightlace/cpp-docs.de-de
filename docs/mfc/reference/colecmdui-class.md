---
title: Klasse COleCmdUI | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- document object server
- COleCmdUI class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
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
ms.openlocfilehash: 38e7019d7636166262028d955455cee675824f8b
ms.lasthandoff: 02/24/2017

---
# <a name="colecmdui-class"></a>COleCmdUI-Klasse
Implementiert eine Methode, die es MFC ermöglicht, den Zustand von Benutzeroberflächenobjekten zu aktualisieren, die in Bezug zu den `IOleCommandTarget`-gesteuerten Funktionen der Anwendung stehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Erstellt ein `COleCmdUI`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Aktiviert oder deaktiviert die Kennzeichnung des Befehls aktivieren.|  
|[COleCmdUI::SetCheck](#setcheck)|Legt den Status einer Umschaltfläche ein-/ausschalten Befehl.|  
|[COleCmdUI::SetText](#settext)|Gibt eine Textzeichenfolge Name oder Status für einen Befehl zurück.|  
  
## <a name="remarks"></a>Hinweise  
 In einer Anwendung, die für DocObjects, nicht aktiviert ist, wenn der Benutzer ein Menü in der Prozesse von MFC-Anwendung zeigt **UPDATE_COMMAND_UI** Benachrichtigungen. Jede Benachrichtigung erhält eine [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt, das bearbeitet werden kann, um den Zustand eines bestimmten Befehls wiederzugeben. Aber wenn Ihre Anwendung für DocObjects aktiviert ist, MFC verarbeitet **UPDATE_OLE_COMMAND_UI** Benachrichtigungen und weist `COleCmdUI` Objekte.  
  
 `COleCmdUI`kann DocObject zum Empfangen von Befehlen, die in der Benutzeroberfläche (z. B. auf Dateineues, öffnen, drucken usw.) des Containers stammen, und einen Container zum Empfangen von Befehlen, die in der Benutzeroberfläche für das Objekt stammen. Obwohl `IDispatch` verwendet werden, um die gleichen Befehle senden `IOleCommandTarget` bietet eine einfachere Möglichkeit zum Abfragen und ausgeführt werden, da er auf einen Standardsatz von Befehlen in der Regel ohne Argumente beruht und keine Typinformationen beteiligt ist. `COleCmdUI`kann verwendet werden, zu aktivieren, aktualisieren und andere Eigenschaften des DocObject Benutzeroberflächenbefehlen festzulegen. Wenn Sie den Befehl aufrufen möchten, rufen [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 Weitere Informationen über DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
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
 Eine Liste der unterstützten Befehle, die die angegebene GUID zugeordnet. Die **OLECMD** Struktur ordnet Befehle Befehlsflags.  
  
 *cCmds*  
 Die Anzahl der Befehle in `rgCmds`.  
  
 `pGroup`  
 Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Das `COleCmdUI` Objekt bietet eine programmgesteuerte Schnittstelle für die Aktualisierung DocObject Benutzeroberflächen-Objekten wie z. B. Menüeinträge oder Control-Schaltflächen. Die Benutzeroberflächen-Objekte können werden aktiviert, deaktiviert, überprüft und/oder deaktiviert, bis die `COleCmdUI` Objekt.  
  
##  <a name="enable"></a>COleCmdUI::Enable  
 Mit dieser Funktion können Sie den Befehl gesetzt, der die `COleCmdUI` -Objekt **OLECOMDF_ENABLED**, der Schnittstelle mit dem Befehl angewiesen ist, verfügbar und aktiviert, oder die Kennzeichnung des Befehls zu löschen.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Parameter  
 `bOn`  
 Gibt an, ob mit dem Befehl verknüpft die `COleCmdUI` Objekt aktiviert oder deaktiviert werden soll. Nonzero kann mit dem Befehl. 0 wird der Befehl deaktiviert.  
  
##  <a name="setcheck"></a>COleCmdUI::SetCheck  
 Mit dieser Funktion können Sie den Status einer Umschaltfläche ein-/ausschalten Befehl.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Ein Wert, der den Status einer Umschaltfläche ein-/ausschalten bestimmt Befehl. Gültige Werte:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**1**|Legt den Befehl auf.|  
|**2**|Legt den Befehl einem unbestimmten Zustand fest. der Status kann nicht bestimmt werden, da das Attribut mit diesem Befehl sowohl ein und aus Status in die entsprechende Auswahl wird.|  
|Jeder andere Wert|Legt den Befehl auf off fest.|  
  
##  <a name="settext"></a>COleCmdUI::SetText  
 Rufen Sie diese Funktion, um eine Textzeichenfolge Name oder Status für einen Befehl zurück.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszText`  
 Ein Zeiger auf den Text, mit dem Befehl verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




