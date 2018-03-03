---
title: Ereigniszuordnungs-Makros (ATL)-Nachricht | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 200d82c9d9b2ca0456ae5de4d6c937be69e212bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="message-map-macros-atl"></a>Meldungszuordnungsmakros (ATL)
Diese Makros definieren nachrichtenzuordnungen und Einträge.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Markiert den Beginn einer alternativen meldungszuordnung.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Markiert den Beginn des Standard-meldungszuordnung.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Der Zertifizierungskette auf eine alternative meldungszuordnung in der Basisklasse.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Der Zertifizierungskette auf eine alternative meldungszuordnung in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Die Ketten für die Standard-meldungszuordnung in der Basisklasse.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|-Ketten für die Nachricht, die zur Laufzeit in einer anderen Klasse zugeordnet werden.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Die Ketten für die Standard-meldungszuordnung in einem Datenmember der Klasse.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[COMMAND_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Implementiert eine leere Nachricht zuordnen.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Reflektierte Meldungen, die nicht, andernfalls verarbeitet werden wird einen Standard-Handler bereit.|  
|[END_MSG_MAP](#end_msg_map)|Markiert das Ende einer meldungszuordnung.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Leitet die benachrichtigungsmeldungen an das übergeordnete Fenster.|  
|[MESSAGE_HANDLER](#message_handler)|Ordnet eine Windows-Nachricht an eine Handlerfunktion.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten an eine Handlerfunktion.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine **WM_NOTIFY** Nachricht für eine Ereignishandler-Funktion, die auf Grundlage des Steuerelements.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Gibt die benachrichtigungsmeldungen an das Fenster, das sie gesendet wurden.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht für eine Ereignishandler-Funktion, die auf Grundlage des Steuerelements.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 Markiert den Beginn einer alternativen meldungszuordnung.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `msgMapID`  
 [in] Der Meldungsbezeichner Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 ATL identifiziert jede Nachricht Zuordnung durch eine Zahl. Die Standard-meldungszuordnung (deklariert mit den `BEGIN_MSG_MAP` Makro) von 0 bezeichnet wird. Eine alternative meldungszuordnung identifizierte `msgMapID`.  
  
 Meldungszuordnungen werden verwendet, um Nachrichten an ein Fenster zu verarbeiten. Beispielsweise [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) können Sie den Bezeichner des einer meldungszuordnung in des enthaltenden Objekts angeben. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) verwendet dann diese meldungszuordnung, um den im Fenster Meldungen an die entsprechenden Handler-Funktion oder auf einem anderen meldungszuordnung weiter. Eine Liste der Makros, die Handlerfunktionen deklarieren, finden Sie unter [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Sie können dann nachfolgende alternativen meldungszuordnungen deklarieren.  
  
 Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Beachten Sie, dass immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Standard-meldungszuordnung und eine alternative meldungszuordnung, jeweils eine Handlerfunktion enthalten:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Markiert den Beginn des Standard-meldungszuordnung.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Der Name der Klasse, die die meldungszuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 [CWindowImpl:: WindowProc](cwindowimpl-class.md#windowproc) verwendet die Standard-meldungszuordnung zum Verarbeiten von Nachrichten an das Fenster gesendet. Die meldungszuordnung leitet Nachrichten an die entsprechenden Handler-Funktion oder einer anderen Nachricht zuordnen.  

  
 Die folgenden Makros eine Nachricht an eine Handlerfunktion zugeordnet. Diese Funktion muss definiert werden, `theClass`.  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Ordnet eine Windows-Nachricht an eine Handlerfunktion.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten an eine Handlerfunktion.|  
|[COMMAND_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet einen zusammenhängenden Bereich von **WM_COMMAND** Nachrichten an eine Handlerfunktion anhand der ID des Menüelements, Steuerelements oder Zugriffstaste.|  
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine **WM_NOTIFY** Nachricht für eine Ereignishandler-Funktion, die auf Grundlage des Steuerelements.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet einen zusammenhängenden Bereich von **WM_NOTIFY** Nachrichten an eine Handlerfunktion auf Grundlage des Steuerelements.|  
  
 Die folgenden Makros verweisen Sie Nachrichten in einer anderen Nachricht zuordnen. Dieser Vorgang wird als "verketten".  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Die Ketten für die Standard-meldungszuordnung in der Basisklasse.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Die Ketten für die Standard-meldungszuordnung in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Der Zertifizierungskette auf eine alternative meldungszuordnung in der Basisklasse.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Der Zertifizierungskette auf eine alternative meldungszuordnung in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Die Ketten für die Standard-meldungszuordnung in einer anderen Klasse zur Laufzeit.|  
  
 Die folgenden Makros weiterleiten "wiedergegeben" Nachrichten über das übergeordnete Fenster. Angenommen, ein Steuerelement normalerweise sendet benachrichtigungsmeldungen an das übergeordnete Fenster für die Verarbeitung, aber das übergeordnete Fenster reflektiert die Nachricht zurück an das Steuerelement.  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht für eine Ereignishandler-Funktion, die auf Grundlage des Steuerelements.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Wenn eine `CMyExtWindow` Objekt empfängt ein `WM_PAINT` Nachricht, an die Nachricht weitergeleitet wird `CMyExtWindow::OnPaint` für die tatsächliche Verarbeitung. Wenn `OnPaint` gibt an, die Nachricht erfordert weitere Verarbeitung der Nachricht wird, und klicken Sie dann auf die Standard-meldungszuordnung in weitergeleitet `CMyBaseWindow`.  
  
 Zusätzlich zu den Standard-meldungszuordnung, können Sie definieren eine alternative meldungszuordnung mit [ALT_MSG_MAP](#alt_msg_map). Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Sie können dann nachfolgende alternativen meldungszuordnungen deklarieren. Das folgende Beispiel zeigt die Standard-meldungszuordnung und eine alternative meldungszuordnung, jeweils eine Handlerfunktion enthalten:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Beachten Sie, dass immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainClass`  
 [in] Der Name der Basisklasse, die nachrichtenzuordnung enthält.  
  
 `msgMapID`  
 [in] Der Meldungsbezeichner Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_ALT`leitet Nachrichten an einen alternativen meldungszuordnung in einer Basisklasse. Sie müssen mit diesem alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Weiterleiten von Nachrichten an eine Basisklasse Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), verwenden Sie `CHAIN_MSG_MAP`. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainMember`  
 [in] Der Name des Datenmembers, enthält die meldungszuordnung.  
  
 `msgMapID`  
 [in] Der Meldungsbezeichner Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_ALT_MEMBER`leitet Nachrichten an einen alternativen meldungszuordnung in einem Datenmember. Sie müssen mit diesem alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Weiterleiten von Nachrichten an einen Datenmember standardmäßig meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), verwenden Sie `CHAIN_MSG_MAP_MEMBER`. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainClass`  
 [in] Der Name der Basisklasse, die nachrichtenzuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP`leitet Nachrichten an eine Basisklasse Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Weiterleiten von Nachrichten an eine Basisklasse alternativen meldungszuordnung (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des Standard-meldungszuordnung und `OnPaint` ist kein Handle eine Nachricht, die Nachricht wird an `CMyBaseClass`des Standard-meldungszuordnung für die Verarbeitung.  
  
-   Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden weitergeleitet, um `CMyBaseClass`des Standard-meldungszuordnung.  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des zweiten alternative Nachricht zuordnen und `OnChar` ist kein Handle eine Nachricht, die Nachricht wird an die angegebene alternative meldungszuordnung in `CMyBaseClass`. `CMyBaseClass`muss mit diesem meldungszuordnung deklariert `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Parameter  
 *dynaChainID*  
 [in] Der eindeutige Bezeichner für ein Objekt meldungszuordnung.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_DYNAMIC`leitet Nachrichten zur Laufzeit, um die Standard-meldungszuordnung in einem anderen Objekt. Das Objekt und seine meldungszuordnung zugeordnet sind *DynaChainID*, die Sie definieren, über [CDynamicChain:: SetChainEntry](cdynamicchain-class.md#setchainentry). Leiten Sie eine Klasse von `CDynamicChain` um verwenden `CHAIN_MSG_MAP_DYNAMIC`. Ein Beispiel finden Sie die [CDynamicChain](../../atl/reference/cdynamicchain-class.md) (Übersicht).  

  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung [BEGIN_MSG_MAP](#begin_msg_map). Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainMember`  
 [in] Der Name des Datenmembers, enthält die meldungszuordnung.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_MEMBER`leitet Nachrichten an einen Datenmember standardmäßig meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Weiterleiten von Nachrichten an einen Datenmember alternativen meldungszuordnung (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung `BEGIN_MSG_MAP`. Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des Standard-meldungszuordnung und `OnPaint` ist kein Handle eine Nachricht, die Nachricht wird an `m_obj`des Standard-meldungszuordnung für die Verarbeitung.  
  
-   Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden weitergeleitet, um `m_obj`des Standard-meldungszuordnung.  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des zweiten alternative Nachricht zuordnen und `OnChar` ist keine Handles, die eine Nachricht, die Nachricht wird an die angegebene alternative meldungszuordnung von `m_obj`. Klasse `CMyContainedClass` muss deklariert diese meldungszuordnung mit `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht schon auf Grundlage der Benachrichtigungscode.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `COMMAND_HANDLER`Ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an die angegebene Handler-Funktion, basierend auf den Benachrichtigungscode und der Bezeichner. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Jede Funktion, die im angegebenen eine `COMMAND_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Die Nachricht Zuordnung Mengen `bHandled` auf **"true"** vor `CommandHandler` aufgerufen wird. Wenn `CommandHandler` behandelt die Nachricht nicht vollständig sollte `bHandled` auf **"false"** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung [BEGIN_MSG_MAP](#begin_msg_map). Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `COMMAND_HANDLER`, können Sie [MESSAGE_HANDLER](#message_handler) Zuordnen einer **WM_COMMAND** Nachricht unabhängig von der einen Bezeichner oder einen Code. In diesem Fall `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` leitet alle **WM_COMMAND** von Nachrichten an `OnHandlerFunction`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht schon auf Grundlage der Bezeichner des Menüelements, Steuerelements oder Zugriffstaste.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste Senden der Nachricht.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), jedoch ordnet [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten mit einer bestimmten Benachrichtigungscode aus einem Bereich von Steuerelementen für eine einzelnes Handlerfunktion.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten aus einem Bereich von Steuerelementen für eine einzelnes Handlerfunktion.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Deklariert eine leere Nachricht zuordnen.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_EMPTY_MSG_MAP`ist eine benutzerfreundliche-Makro, das Aufrufe der Makros [BEGIN_MSG_MAP](#begin_msg_map) und [END_MSG_MAP](#end_msg_map) eine leere nachrichtenzuordnung erstellen:  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Bietet ein Standard-Handler für das untergeordnete Fenster (Steuerelement), das empfangen Nachrichten reflektiert. der Handler wird nicht verarbeitete Nachrichten ordnungsgemäß übergeben `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 Markiert das Ende einer meldungszuordnung.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie immer die [BEGIN_MSG_MAP](#begin_msg_map) Makro mit den Anfang einer meldungszuordnung markiert. Verwendung [ALT_MSG_MAP](#alt_msg_map) nachfolgende alternativen meldungszuordnungen zu deklarieren.  
  
 Beachten Sie, dass immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Standard-meldungszuordnung und eine alternative meldungszuordnung, jeweils eine Handlerfunktion enthalten:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Leitet die benachrichtigungsmeldungen an das übergeordnete Fenster.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird als Teil Ihrer meldungszuordnung angeben.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Parameter  
 `msg`  
 [in] Die Windows-Meldung.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `MESSAGE_HANDLER`Ordnet eine Windows-Meldung an die angegebene Handler-Funktion.  
  
 Jede Funktion, die im angegebenen eine `MESSAGE_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Die Nachricht Zuordnung Mengen `bHandled` auf **"true"** vor `MessageHandler` aufgerufen wird. Wenn `MessageHandler` behandelt die Nachricht nicht vollständig sollte `bHandled` auf **"false"** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung [BEGIN_MSG_MAP](#begin_msg_map). Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `MESSAGE_HANDLER`, können Sie [COMMAND_HANDLER](#command_handler) und [NOTIFY_HANDLER](#notify_handler) abzubildenden [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) und [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten, bzw.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Ähnlich wie [MESSAGE_HANDLER](#message_handler), aber einen Bereich von Windows-an einen einzelnen Handlerfunktion Nachrichten Zuordnungen.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 *msgFirst*  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Nachrichten.  
  
 *msgLast*  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Nachrichten.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht schon auf Grundlage der Benachrichtigungscode.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Parameter  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 Definiert einen Eintrag in einer meldungszuordnung.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Steuerelements, das Senden der Nachricht.  
  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `NOTIFY_HANDLER`Ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht an die angegebene Handler-Funktion, basierend auf den Benachrichtigungscode und der Bezeichner.  
  
 Jede Funktion, die im angegebenen eine `NOTIFY_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Die Nachricht Zuordnung Mengen `bHandled` auf **"true"** vor `NotifyHandler` aufgerufen wird. Wenn `NotifyHandler` behandelt die Nachricht nicht vollständig sollte `bHandled` auf **"false"** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen immer mit eine meldungszuordnung [BEGIN_MSG_MAP](#begin_msg_map). Dann können Sie nachfolgende alternativen meldungszuordnungen mit deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der meldungszuordnung. Jeder nachrichtenzuordnung muss genau eine Instanz haben `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `NOTIFY_HANDLER`, können Sie [MESSAGE_HANDLER](#message_handler) Zuordnen einer **WM_NOTIFY** Nachricht unabhängig von der einen Bezeichner oder einen Code. In diesem Fall `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` leitet alle **WM_NOTIFY** von Nachrichten an `OnHandlerFunction`.  
  
 Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht nur auf Grundlage des Steuerelements.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Steuerelements, das Senden der Nachricht.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch ordnet [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten mit einer bestimmten Benachrichtigungscode aus einem Bereich von Steuerelementen für eine einzelnes Handlerfunktion.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Steuerelements, das Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten aus einem Bereich von Steuerelementen für eine einzelnes Handlerfunktion.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Steuerelements, das Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Gibt die benachrichtigungsmeldungen an das untergeordnete Fenster (Steuerelement), das sie gesendet.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird als Teil des übergeordneten Fensters meldungszuordnung angeben.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Ähnlich wie [COMMAND_CODE_HANDLER](#command_code_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Ähnlich wie [COMMAND_ID_HANDLER](#command_id_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `code`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Ähnlich wie [NOTIFY_CODE_HANDLER](#notify_code_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Ähnlich wie [NOTIFY_ID_HANDLER](#notify_id_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner der dem Menüelement, Steuerelement oder Zugriffstaste.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `cd`  
 [in] Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden   
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster wiedergegeben.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Nachrichtenhandler Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
