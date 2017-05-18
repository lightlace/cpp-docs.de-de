---
title: Meldung Makros (ATL) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8097982d6574af2ce1ba592dbead8abf6f6433df
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-atl"></a>Meldungszuordnungsmakros (ATL)
Diese Makros definieren Meldungszuordnungstabellen und Einträge.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Markiert den Beginn einer Zuordnung alternative Nachricht.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Markiert den Beginn der Zuordnung standardmäßig angezeigt.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Ketten zu einer anderen Nachricht zuordnen in der Basisklasse.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Ordnen Sie Ketten an eine andere Nachricht in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Verkettet die Standardnachricht zuordnen in der Basisklasse.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Ordnen Sie Ketten für die Nachricht in einer anderen Klasse zur Laufzeit.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Verkettet die Standardnachricht zuordnen in einem Datenmember der Klasse.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[COMMAND_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und die ID des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Implementiert eine leere Nachricht zuordnen.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Stellt einen Standardhandler für reflektierte Meldungen, die andernfalls nicht behandelt werden.|  
|[END_MSG_MAP](#end_msg_map)|Markiert das Ende einer Zuordnung angezeigt.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Leitet die Benachrichtigung an das übergeordnete Fenster.|  
|[MESSAGE_HANDLER AUS](#message_handler)|Wird eine Windows-Nachricht eine Handlerfunktion zugeordnet.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten eine Handlerfunktion.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Steuerelements.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Gibt die Benachrichtigung an das Fenster, das sie gesendet wurden.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und die ID des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Steuerelements.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 Markiert den Beginn einer Zuordnung alternative Nachricht.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `msgMapID`  
 [in] Der Meldungsbezeichner zuordnen.  
  
### <a name="remarks"></a>Hinweise  
 ATL identifiziert jede Nachricht Zuordnung durch eine Zahl. Die Nachricht Standardkurve (deklariert mit der `BEGIN_MSG_MAP` Makro) wird durch 0 identifiziert. Eine alternative meldungszuordnung identifizierten `msgMapID`.  
  
 Meldungszuordnungen werden zum Verarbeiten von Nachrichten, die an ein Fenster gesendet. Beispielsweise [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) können Sie den Bezeichner einer Nachricht Zuordnung in dem Objekt angeben. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) verwendet dann den im Fenster Nachrichten an die entsprechenden Handler-Funktion oder eine andere Nachricht Zuordnung Weiterleiten dieser Nachricht zuordnen. Eine Liste der Makros, die Handlerfunktionen deklarieren, finden Sie unter [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann nachfolgende alternativen Meldungszuordnungstabellen deklarieren.  
  
 Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Beachten Sie, dass es immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Standardkurve Nachricht und einer anderen Nachricht zuordnen, jeweils eine Handlerfunktion:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Markiert den Beginn der Zuordnung standardmäßig angezeigt.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Der Name der Klasse, die die Zuordnung der Nachricht enthält.  
  
### <a name="remarks"></a>Hinweise  
 [CWindowImpl:: WindowProc](cwindowimpl-class.md#windowproc) verwendet die Standard-Nachricht-Zuordnung zum Verarbeiten von Nachrichten, die an das Fenster gesendet. Die Zuordnung der Nachricht leitet Nachrichten an die entsprechenden Handler-Funktion oder eine andere Nachricht-Zuordnung.  

  
 Die folgenden Makros eine Nachricht an eine Handlerfunktion zugeordnet. Diese Funktion muss definiert werden, `theClass`.  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[MESSAGE_HANDLER AUS](#message_handler)|Wird eine Windows-Nachricht eine Handlerfunktion zugeordnet.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten eine Handlerfunktion.|  
|[COMMAND_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und die ID des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Ordnet eine **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet einen zusammenhängenden Bereich von **WM_COMMAND** Nachrichten an eine Handlerfunktion basierend auf den Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Steuerelements.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet einen zusammenhängenden Bereich von **WM_NOTIFY** Nachrichten an eine Handlerfunktion anhand der Bezeichner.|  
  
 Die folgenden Makros Weiterleitung der Nachrichten an eine andere Nachricht zuordnen. Diesen Prozess nennt "verketten".  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Verkettet die Standardnachricht zuordnen in der Basisklasse.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Verkettet die Standardnachricht zuordnen in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Ketten zu einer anderen Nachricht zuordnen in der Basisklasse.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Ordnen Sie Ketten an eine andere Nachricht in einem Datenmember der Klasse.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Verkettet die Standardnachricht zuordnen in einer anderen Klasse zur Laufzeit.|  
  
 Die folgenden Makros direkte "reflektiert" Nachrichten aus dem übergeordneten Fenster. Angenommen, ein Steuerelement normalerweise sendet Nachrichten an das übergeordnete Fenster für die Verarbeitung, aber das übergeordnete Fenster reflektiert die Nachricht an das Steuerelement.  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und die ID des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte **WM_COMMAND** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und der Bezeichner.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Bezeichner des Steuerelements.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte **WM_NOTIFY** Nachricht an eine Handlerfunktion, basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs.|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#102;](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Wenn ein `CMyExtWindow` Objekt erhält einen `WM_PAINT` Nachricht die Nachricht wird angewiesen, `CMyExtWindow::OnPaint` für die eigentliche Verarbeitung. Wenn `OnPaint` gibt an, die Nachricht erfordert weitere Verarbeitung der Nachricht wird dann an die Nachricht Standardkurve in geleitet `CMyBaseWindow`.  
  
 Neben der Nachricht die Standardkurve können eine alternative meldungszuordnung mit [ALT_MSG_MAP](#alt_msg_map). Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann nachfolgende alternativen Meldungszuordnungstabellen deklarieren. Das folgende Beispiel zeigt die Standardkurve Nachricht und einer anderen Nachricht zuordnen, jeweils eine Handlerfunktion:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Beachten Sie, dass es immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainClass`  
 [in] Der Name der Basisklasse, die Zuordnung der Nachricht enthält.  
  
 `msgMapID`  
 [in] Der Meldungsbezeichner zuordnen.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_ALT`leitet Nachrichten an eine andere Nachricht Zuordnung in einer Basisklasse. Sie müssen diese alternativen meldungszuordnung mit deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Weiterleiten von Nachrichten an eine Basisklasse Nachricht Standardkurve (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), verwenden Sie `CHAIN_MSG_MAP`. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainMember`  
 [in] Der Name des Datenmembers mit der Zuordnung angezeigt.  
  
 `msgMapID`  
 [in] Der Meldungsbezeichner zuordnen.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_ALT_MEMBER`leitet Nachrichten an eine andere Nachricht Zuordnung in einem Datenmember. Sie müssen diese alternativen meldungszuordnung mit deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Weiterleiten von Nachrichten an ein Datenelement Nachricht Standardkurve (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), verwenden Sie `CHAIN_MSG_MAP_MEMBER`. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainClass`  
 [in] Der Name der Basisklasse, die Zuordnung der Nachricht enthält.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP`leitet Nachrichten an eine Basisklasse Nachricht Standardkurve (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Weiterleiten von Nachrichten an eine Basisklasse alternativen meldungszuordnung (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#107;](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des Standardkurve Nachricht und `OnPaint` nicht Handle eine Nachricht und die Nachricht angewiesen wird, `CMyBaseClass`Nachricht Standardkurve für die Verarbeitung.  
  
-   Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden angewiesen, `CMyBaseClass`des Standardkurve Nachricht.  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des zweiten alternative Nachricht zuordnen und `OnChar` ist kein Handle eine Nachricht und die Nachricht, die Zuordnung der angegebenen alternativen Nachricht im angewiesen wird `CMyBaseClass`. `CMyBaseClass`muss deklariert diese Nachricht Zuordnung mit `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Parameter  
 *dynaChainID*  
 [in] Der eindeutige Bezeichner für ein Objekt Nachricht zuordnen.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_DYNAMIC`leitet Nachrichten zur Laufzeit, um die Standardkurve für die Nachricht in einem anderen Objekt. Das Objekt und seine meldungszuordnung im Zusammenhang mit *DynaChainID*, das Sie durch definieren [CDynamicChain:: SetChainEntry](cdynamicchain-class.md#setchainentry). Leiten Sie eine Klasse von `CDynamicChain` um verwenden `CHAIN_MSG_MAP_DYNAMIC`. Ein Beispiel finden Sie unter der [CDynamicChain](../../atl/reference/cdynamicchain-class.md) (Übersicht).  

  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Parameter  
 `theChainMember`  
 [in] Der Name des Datenmembers mit der Zuordnung angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 `CHAIN_MSG_MAP_MEMBER`leitet Nachrichten an ein Datenelement Nachricht Standardkurve (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Weiterleiten von Nachrichten an ein Datenelement alternativen meldungszuordnung (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit `BEGIN_MSG_MAP`. Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren `ALT_MSG_MAP`. Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#108;](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Dieses Beispiel veranschaulicht Folgendes:  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des Standardkurve Nachricht und `OnPaint` nicht Handle eine Nachricht und die Nachricht angewiesen wird, `m_obj`Nachricht Standardkurve für die Verarbeitung.  
  
-   Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden angewiesen, `m_obj`des Standardkurve Nachricht.  
  
-   Wenn eine Fensterprozedur verwendet `CMyClass`des zweiten alternative Nachricht zuordnen und `OnChar` ist kein Handle eine Nachricht und die Nachricht wird an der angegebenen alternativen meldungszuordnung der geleitet `m_obj`. Klasse `CMyContainedClass` muss deklariert diese Nachricht Zuordnung mit `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht nur anhand der Benachrichtigungscode.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.  
  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `COMMAND_HANDLER`Ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an die angegebene Handler-Funktion, basierend auf den Benachrichtigungscode und der Bezeichner. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Windowing&#119;](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Jede Funktion, die gemäß einer `COMMAND_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Die Zuordnung Nachrichtensätze `bHandled` auf **TRUE** vor `CommandHandler` aufgerufen wird. Wenn `CommandHandler` die Meldung nicht vollständig verarbeitet sollte `bHandled` auf **FALSE** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `COMMAND_HANDLER`, können Sie [MESSAGE_HANDLER](#message_handler) Zuordnen einer **WM_COMMAND** Nachricht einen Bezeichner oder Code. In diesem Fall `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` leitet alle **WM_COMMAND** Nachrichten `OnHandlerFunction`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht nur auf Grundlage des Bezeichners des Menüelements, Steuerelements oder Accelerator.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder Accelerator Senden der Nachricht.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), jedoch ordnet [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten mit einem bestimmten Benachrichtigung aus einer Reihe von Steuerelementen auf einem einzelnen Handler-Funktion.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Menüelements, Steuerelements oder Accelerator Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten aus einer Reihe von Steuerelementen zu einem einzelnen Handler-Funktion.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Menüelements, Steuerelements oder Accelerator Senden der Nachricht.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Deklariert eine leere Nachricht zuordnen.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 `DECLARE_EMPTY_MSG_MAP`ist eine der Einfachheit halber-Makro, das die Makros ruft [BEGIN_MSG_MAP](#begin_msg_map) und [END_MSG_MAP](#end_msg_map) eine leere Nachricht Zuordnung erstellen:  
  
 [!code-cpp[NVC_ATL_Windowing&#122;](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Bietet ein Standardhandler für das untergeordnete Fenster (Steuerelement), das erhalten Nachrichten berücksichtigt; der Handler übergibt die nicht verarbeitete Nachrichten ordnungsgemäß `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 Markiert das Ende einer Zuordnung angezeigt.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie immer die [BEGIN_MSG_MAP](#begin_msg_map) Makro, um den Anfang einer Nachricht Karte markieren. Verwendung [ALT_MSG_MAP](#alt_msg_map) nachfolgende alternativen Meldungszuordnungstabellen deklarieren.  
  
 Beachten Sie, dass es immer genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Standardkurve Nachricht und einer anderen Nachricht zuordnen, jeweils eine Handlerfunktion:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Leitet die Benachrichtigung an das übergeordnete Fenster.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie dieses Makro als Teil der Zuordnung angezeigt.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER AUS  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Parameter  
 `msg`  
 [in] Die Windows-Meldung.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `MESSAGE_HANDLER`Ordnet eine Windows-Meldung an die angegebene Handler-Funktion.  
  
 Jede Funktion, die gemäß einer `MESSAGE_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Die Zuordnung Nachrichtensätze `bHandled` auf **TRUE** vor `MessageHandler` aufgerufen wird. Wenn `MessageHandler` die Meldung nicht vollständig verarbeitet sollte `bHandled` auf **FALSE** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `MESSAGE_HANDLER`, können Sie [COMMAND_HANDLER](#command_handler) und [NOTIFY_HANDLER](#notify_handler) zuordnen [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) und [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten bzw..  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#129;](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Ähnlich wie [MESSAGE_HANDLER](#message_handler), jedoch in einer Vielzahl von Windows-an einen einzelnen Handlerfunktion Nachrichten zugeordnet.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 *msgFirst*  
 [in] Markiert den Anfang einen zusammenhängenden Bereich von Nachrichten.  
  
 *msgLast*  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Nachrichten.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht nur anhand der Benachrichtigungscode.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Parameter  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 Definiert einen Eintrag in einer Karte angezeigt.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Steuerelements, das die Nachricht gesendet.  
  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 `NOTIFY_HANDLER`Ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht an die angegebene Handler-Funktion, basierend auf den Benachrichtigungscode und der Bezeichner.  
  
 Jede Funktion, die gemäß einer `NOTIFY_HANDLER` Makro muss wie folgt definiert werden:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Die Zuordnung Nachrichtensätze `bHandled` auf **TRUE** vor `NotifyHandler` aufgerufen wird. Wenn `NotifyHandler` die Meldung nicht vollständig verarbeitet sollte `bHandled` auf **FALSE** an, dass die Nachricht noch weitere Verarbeitung erforderlich.  
  
> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen Meldungszuordnungstabellen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro kennzeichnet das Ende der Zuordnung angezeigt. Jeder Nachricht Zuordnung müssen genau eine Instanz des `BEGIN_MSG_MAP` und `END_MSG_MAP`.  
  
 Zusätzlich zu `NOTIFY_HANDLER`, können Sie [MESSAGE_HANDLER](#message_handler) Zuordnen einer **WM_NOTIFY** Nachricht einen Bezeichner oder Code. In diesem Fall `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` leitet alle **WM_NOTIFY** Nachrichten `OnHandlerFunction`.  
  
 Weitere Informationen zur Verwendung von Meldungszuordnungstabellen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#130;](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachricht nur anhand der Bezeichner.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Steuerelements, das die Nachricht gesendet.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch ordnet [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten mit einem bestimmten Benachrichtigung aus einer Reihe von Steuerelementen auf einem einzelnen Handler-Funktion.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Steuerelements, das die Nachricht gesendet.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) Nachrichten aus einer Reihe von Steuerelementen zu einem einzelnen Handler-Funktion.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Bereich basiert auf den Bezeichner des Steuerelements, das die Nachricht gesendet.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Gibt die Benachrichtigung an das untergeordnete Fenster (Steuerelement), das sie gesendet wurden.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie dieses Makro als Teil des übergeordneten Fensters Nachricht zuordnen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Ähnlich wie [COMMAND_CODE_HANDLER](#command_code_handler), aber die Befehle aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Ähnlich wie [COMMAND_HANDLER](#command_handler), aber die Befehle aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.  
  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Ähnlich wie [COMMAND_ID_HANDLER](#command_id_handler), aber die Befehle aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), aber die Befehle aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `code`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), aber die Befehle aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Ähnlich wie [NOTIFY_CODE_HANDLER](#notify_code_handler), jedoch Benachrichtigungen aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch Benachrichtigungen aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.  
  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Ähnlich wie [NOTIFY_ID_HANDLER](#notify_id_handler), jedoch Benachrichtigungen aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Menüelements, Steuerelements oder der Zugriffstaste.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), jedoch Benachrichtigungen aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `cd`  
 [in] Der Benachrichtigungscode.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch Benachrichtigungen aus dem übergeordneten Fenster wiedergegeben wird.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Parameter  
 `idFirst`  
 [in] Markiert den Beginn einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `idLast`  
 [in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `func`  
 [in] Der Name der Meldungshandler Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

