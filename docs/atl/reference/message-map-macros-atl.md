---
title: Meldungszuordnungsmakros (ATL)
ms.date: 11/04/2016
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
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: bedef3a8563e27f72017720530e3b7addb78ec3d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290377"
---
# <a name="message-map-macros-atl"></a>Meldungszuordnungsmakros (ATL)

Diese Makros definieren nachrichtenzuordnungen und Einträge.

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|Markiert den Beginn des einen alternativen meldungszuordnung.|
|[BEGIN_MSG_MAP](#begin_msg_map)|Kennzeichnet den Anfang der Standard-meldungszuordnung.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Ordnen Sie Ketten für eine andere Meldung angezeigt, in der Basisklasse.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Ordnen Sie Ketten für eine andere Meldung angezeigt, in einem Datenmember der Klasse.|
|[CHAIN_MSG_MAP](#chain_msg_map)|-Ketten für die Standard-meldungszuordnung in der Basisklasse.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|-Ketten für die Nachricht, die zur Laufzeit in einer anderen Klasse zugeordnet werden.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|-Ketten für die Standard-meldungszuordnung in einem Datenmember der Klasse.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|Ordnet eine Handlerfunktion, die basierend auf dem Notification-Code zu eine WM_COMMAND-Meldung.|
|[COMMAND_HANDLER](#command_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Implementiert eine leere Nachricht zuordnen.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Bietet einen Standardhandler für reflektierter Meldungen, die andernfalls nicht verarbeitet werden.|
|[END_MSG_MAP](#end_msg_map)|Markiert das Ende einer meldungszuordnung.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Leitet die benachrichtigungsmeldungen an das übergeordnete Fenster.|
|[MESSAGE_HANDLER](#message_handler)|Ordnet eine Windows-Meldung an eine Handlerfunktion.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten an eine Handlerfunktion.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und die Steuerelement-ID an.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die auf Grundlage des Steuerelement-ID an.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Gibt Nachrichten zurück an das Fenster, das sie gesendet wurden.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und die Steuerelement-ID an.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die auf Grundlage des Steuerelement-ID an.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="alt_msg_map"></a>  ALT_MSG_MAP

Markiert den Beginn des einen alternativen meldungszuordnung.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>Parameter

*msgMapID*<br/>
[in] Der Nachrichtenbezeichner zuordnen.

### <a name="remarks"></a>Hinweise

ATL wird jede Nachricht Zuordnung durch eine Reihe identifiziert. Die Standard-meldungszuordnung (deklariert mit dem Makro BEGIN_MSG_MAP) wird durch 0 angegeben. Eine alternative meldungszuordnung identifizierte *MsgMapID*.

Meldungszuordnungen werden verwendet, um Nachrichten an ein Fenster zu verarbeiten. Z. B. [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) können Sie den Bezeichner des eine meldungszuordnung in dem Objekt angeben. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) verwendet dann diese meldungszuordnung, leiten Sie den im Fenster Nachrichten an die entsprechenden Handler-Funktion oder an einen anderen meldungszuordnung. Eine Liste der Makros, die Handlerfunktionen zu deklarieren, finden Sie unter [BEGIN_MSG_MAP](#begin_msg_map).

Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen deklarieren.

Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Beachten Sie, dass immer genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP vorhanden ist.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Standard-meldungszuordnung und die Zuordnung für eine andere Meldung angezeigt, jeweils eine Handlerfunktion:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="begin_msg_map"></a>  BEGIN_MSG_MAP

Kennzeichnet den Anfang der Standard-meldungszuordnung.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
[in] Der Name der Klasse, die die meldungszuordnung enthält.

### <a name="remarks"></a>Hinweise

[CWindowImpl:: WindowProc](cwindowimpl-class.md#windowproc) verwendet die Standard-meldungszuordnung zum Verarbeiten von Nachrichten an das Fenster gesendet. Die meldungszuordnung leitet Nachrichten an die entsprechenden Handler-Funktion oder an einer anderen Nachricht zuordnen.

Die folgenden Makros, die eine Nachricht an eine Handlerfunktion zugeordnet. Diese Funktion muss definiert werden, *TheClass*.

|Makro|Beschreibung|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Ordnet eine Windows-Meldung an eine Handlerfunktion.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Ordnet einen zusammenhängenden Bereich von Windows-Nachrichten an eine Handlerfunktion.|
|[COMMAND_HANDLER](#command_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Ordnet eine WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[COMMAND_CODE_HANDLER](#command_handler)|Ordnet eine Handlerfunktion, die basierend auf dem Notification-Code zu eine WM_COMMAND-Meldung.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Ordnet einen zusammenhängenden Bereich von WM_COMMAND-Meldungen an eine Handlerfunktion, die basierend auf den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[NOTIFY_HANDLER](#notify_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und die Steuerelement-ID an.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, die auf Grundlage des Steuerelement-ID an.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Ordnet eine WM_NOTIFY-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Ordnet einen zusammenhängenden Bereich von WM_NOTIFY-Meldungen an eine Handlerfunktion, die auf Grundlage des Steuerelement-ID an.|

Die folgenden Makros leiten Nachrichten an einen anderen meldungszuordnung. Dieser Vorgang wird "verketten" bezeichnet.

|Makro|Beschreibung|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|-Ketten für die Standard-meldungszuordnung in der Basisklasse.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|-Ketten für die Standard-meldungszuordnung in einem Datenmember der Klasse.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Ordnen Sie Ketten für eine andere Meldung angezeigt, in der Basisklasse.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Ordnen Sie Ketten für eine andere Meldung angezeigt, in einem Datenmember der Klasse.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|-Ketten für die Standardnachricht, die zur Laufzeit in einer anderen Klasse zugeordnet werden.|

Die folgenden Makros direkte "wiedergegeben" Nachrichten über das übergeordnete Fenster. Z. B. ein Steuerelement normalerweise sendet benachrichtigungsmeldungen an das übergeordnete Fenster für die Verarbeitung, aber das übergeordnete Fenster kann die Nachricht an das Steuerelement widerspiegeln.

|Makro|Beschreibung|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Bezeichner der dem Menüelement-Steuerelement oder Accelerator.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Ordnet eine reflektierte WM_COMMAND-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und die Steuerelement-ID an.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die auf Grundlage des Steuerelement-ID an.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, basierend auf dem Notification-Code.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf einen zusammenhängenden Bereich von Steuerelement-IDs an.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Ordnet eine reflektierte WM_NOTIFY-Meldung an eine Handlerfunktion, die basierend auf den Benachrichtigungscode und einen zusammenhängenden Bereich von Steuerelement-IDs an.|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

Wenn eine `CMyExtWindow` -Objekt eine WM_PAINT-Nachricht empfängt, die Nachricht weitergeleitet wird, um `CMyExtWindow::OnPaint` für die eigentliche Verarbeitung. Wenn `OnPaint` gibt an, die Nachricht weiter verarbeitet, die Nachricht automatisch werden muss, und klicken Sie dann auf die Standard-meldungszuordnung in geleitet werden `CMyBaseWindow`.

Neben der Standard-meldungszuordnung, können Sie definieren, mit einer alternativen meldungszuordnung [ALT_MSG_MAP](#alt_msg_map). Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen deklarieren. Das folgende Beispiel zeigt die Standard-meldungszuordnung und die Zuordnung für eine andere Meldung angezeigt, jeweils eine Handlerfunktion:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Beachten Sie, dass immer genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP vorhanden ist.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="chain_msg_map_alt"></a>  CHAIN_MSG_MAP_ALT

Definiert einen Eintrag in einer meldungszuordnung.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>Parameter

*theChainClass*<br/>
[in] Der Name der Basisklasse, die die meldungszuordnung enthält.

*msgMapID*<br/>
[in] Der Nachrichtenbezeichner zuordnen.

### <a name="remarks"></a>Hinweise

CHAIN_MSG_MAP_ALT leitet Nachrichten an einen alternativen meldungszuordnung in einer Basisklasse. Sie müssen mit diesem alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Übermitteln von Nachrichten zur meldungszuordnung für eine Basisklasse-Standard (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), CHAIN_MSG_MAP verwenden. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP](#chain_msg_map).

> [!NOTE]
>  Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen mit ALT_MSG_MAP deklarieren. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="chain_msg_map_alt_member"></a>  CHAIN_MSG_MAP_ALT_MEMBER

Definiert einen Eintrag in einer meldungszuordnung.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>Parameter

*theChainMember*<br/>
[in] Der Name des Datenmembers, enthält die meldungszuordnung.

*msgMapID*<br/>
[in] Der Nachrichtenbezeichner zuordnen.

### <a name="remarks"></a>Hinweise

CHAIN_MSG_MAP_ALT_MEMBER leitet Nachrichten an einen alternativen meldungszuordnung in einen Datenmember. Sie müssen mit diesem alternativen meldungszuordnung deklariert [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Um Nachrichten an einen Datenmember des Standard-meldungszuordnung weiterzuleiten (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)), CHAIN_MSG_MAP_MEMBER verwenden. Ein Beispiel finden Sie unter [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).

> [!NOTE]
>  Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen mit ALT_MSG_MAP deklarieren. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="chain_msg_map"></a>  CHAIN_MSG_MAP

Definiert einen Eintrag in einer meldungszuordnung.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>Parameter

*theChainClass*<br/>
[in] Der Name der Basisklasse, die die meldungszuordnung enthält.

### <a name="remarks"></a>Hinweise

CHAIN_MSG_MAP leitet Nachrichten an eine Basisklasse des Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Übermitteln von Nachrichten zur alternativen meldungszuordnung für eine Basisklasse (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).

> [!NOTE]
>  Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen mit ALT_MSG_MAP deklarieren. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

Dieses Beispiel veranschaulicht Folgendes:

- Wenn eine Fensterprozedur verwendet `CMyClass`des Standard-meldungszuordnung und `OnPaint` ist keine Handles, die eine Nachricht, die Nachricht wird an `CMyBaseClass`des Standard-meldungszuordnung für die Verarbeitung.

- Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden weitergeleitet, dass `CMyBaseClass`des Standard-meldungszuordnung.

- Wenn eine Fensterprozedur verwendet `CMyClass`der zweiten alternative Meldung zugeordnet und `OnChar` ist keine Handles, die eine Nachricht, die Nachricht wird in der angegebenen alternativen meldungszuordnung an `CMyBaseClass`. `CMyBaseClass` müssen diese meldungszuordnung mit ALT_MSG_MAP(1) deklariert haben.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="chain_msg_map_dynamic"></a>  CHAIN_MSG_MAP_DYNAMIC

Definiert einen Eintrag in einer meldungszuordnung.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>Parameter

*dynaChainID*<br/>
[in] Der eindeutige Bezeichner für ein Objekt in der meldungszuordnung.

### <a name="remarks"></a>Hinweise

CHAIN_MSG_MAP_DYNAMIC leitet Nachrichten zur Laufzeit, um die Standard-meldungszuordnung in einem anderen Objekt. Das Objekt und seine meldungszuordnung, zugeordnet sind *DynaChainID*, das Sie durch definieren [CDynamicChain:: SetChainEntry](cdynamicchain-class.md#setchainentry). Leiten Sie müssen Ihre Klasse von `CDynamicChain` um CHAIN_MSG_MAP_DYNAMIC verwenden. Ein Beispiel finden Sie unter den [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Übersicht.

> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann die nachfolgenden alternativen meldungszuordnungen mit ALT_MSG_MAP deklarieren. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="chain_msg_map_member"></a>  CHAIN_MSG_MAP_MEMBER

Definiert einen Eintrag in einer meldungszuordnung.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>Parameter

*theChainMember*<br/>
[in] Der Name des Datenmembers, enthält die meldungszuordnung.

### <a name="remarks"></a>Hinweise

CHAIN_MSG_MAP_MEMBER leitet Nachrichten an einen Datenmember des Standard-meldungszuordnung (deklariert mit [BEGIN_MSG_MAP](#begin_msg_map)). Um Nachrichten an einen Datenmember alternativen meldungszuordnung weiterzuleiten (deklariert mit [ALT_MSG_MAP](#alt_msg_map)), verwenden Sie [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).

> [!NOTE]
>  Beginnen Sie immer einer meldungszuordnung mit BEGIN_MSG_MAP. Sie können dann die nachfolgenden alternativen meldungszuordnungen mit ALT_MSG_MAP deklarieren. Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

Dieses Beispiel veranschaulicht Folgendes:

- Wenn eine Fensterprozedur verwendet `CMyClass`des Standard-meldungszuordnung und `OnPaint` ist keine Handles, die eine Nachricht, die Nachricht wird an `m_obj`des Standard-meldungszuordnung für die Verarbeitung.

- Wenn eine Fensterprozedur die erste Alternative meldungszuordnung in verwendet `CMyClass`, alle Nachrichten werden weitergeleitet, dass `m_obj`des Standard-meldungszuordnung.

- Wenn eine Fensterprozedur verwendet `CMyClass`der zweiten alternative Meldung zugeordnet und `OnChar` ist keine Handles, die eine Nachricht, die Nachricht wird von der angegebenen alternativen meldungszuordnung an `m_obj`. Klasse `CMyContainedClass` muss diese meldungszuordnung mit ALT_MSG_MAP(1) deklariert.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="command_code_handler"></a>  COMMAND_CODE_HANDLER

Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht nur anhand der Benachrichtigungscode.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="command_handler"></a>  COMMAND_HANDLER

Definiert einen Eintrag in einer meldungszuordnung.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

COMMAND_HANDLER ordnet eine [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht an die angegebenen Handler-Funktion, die auf der Grundlage der Benachrichtigungscode und der Bezeichner des. Zum Beispiel:

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

Jede Funktion, die in einem Makro COMMAND_HANDLER angegebenen muss wie folgt definiert werden:

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

Die Zuordnung Nachrichtensätze `bHandled` auf "true", bevor Sie `CommandHandler` aufgerufen wird. Wenn `CommandHandler` ist nicht vollständig verarbeitet die Nachricht sollte `bHandled` auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen meldungszuordnungen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Zusätzlich zu COMMAND_HANDLER, können Sie [MESSAGE_HANDLER aus](#message_handler) eine WM_COMMAND-Meldung ohne Berücksichtigung der einen Bezeichner oder Code zuordnen. In diesem Fall `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` leitet alle WM_COMMAND-Meldungen in `OnHandlerFunction`.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="command_id_handler"></a>  COMMAND_ID_HANDLER

Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet eine [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht nur auf Grundlage des Bezeichners des Menüelements, Control oder Accelerator.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner, der die Menüelement-Steuerelement oder Zugriffstaste, die die Nachricht gesendet werden soll.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="command_range_code_handler"></a>  COMMAND_RANGE_CODE_HANDLER

Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), jedoch ordnet [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten mit einem bestimmten Benachrichtigungscode aus einem Bereich von Steuerelementen zu einer einzelnen Handler-Funktion.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

Dieser Bereich basiert auf den Bezeichner der die Menüelement-Steuerelement oder Accelerator Senden der Nachricht.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="command_range_handler"></a>  COMMAND_RANGE_HANDLER

Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten aus einem Bereich von Steuerelementen zu einer einzelnen Handler-Funktion.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

Dieser Bereich basiert auf den Bezeichner der die Menüelement-Steuerelement oder Accelerator Senden der Nachricht.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="declare_empty_msg_map"></a>  DECLARE_EMPTY_MSG_MAP

Deklariert eine Zuordnung für die leere Nachricht an.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>Hinweise

DECLARE_EMPTY_MSG_MAP ist einer der Einfachheit halber-Makro, das die Makros, die Aufrufe [BEGIN_MSG_MAP](#begin_msg_map) und [END_MSG_MAP](#end_msg_map) um eine leere Nachricht zu erstellen:

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

##  <a name="default_reflection_handler"></a>  DEFAULT_REFLECTION_HANDLER

Bietet ein Standard-Handler für das untergeordnete Fenster (Steuerelement), das erhält Nachrichten berücksichtigt; der Handler für nicht behandelte Meldungen zu ordnungsgemäß übergibt `DefWindowProc`.

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="end_msg_map"></a>  END_MSG_MAP

Markiert das Ende einer meldungszuordnung.

```
END_MSG_MAP()
```

### <a name="remarks"></a>Hinweise

Verwenden Sie immer die [BEGIN_MSG_MAP](#begin_msg_map) Makro, um den Anfang einer meldungszuordnung markieren. Verwendung [ALT_MSG_MAP](#alt_msg_map) nachfolgende alternativen meldungszuordnungen zu deklarieren.

Beachten Sie, dass immer genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP vorhanden ist.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Standard-meldungszuordnung und die Zuordnung für eine andere Meldung angezeigt, jeweils eine Handlerfunktion:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

Das nächste Beispiel zeigt zwei alternativen meldungszuordnungen. Die Standard-meldungszuordnung ist leer.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="forward_notifications"></a>  FORWARD_NOTIFICATIONS

Leitet die benachrichtigungsmeldungen an das übergeordnete Fenster.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>Hinweise

Dieses Makro wird als Teil Ihrer meldungszuordnung angeben.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="message_handler"></a>  MESSAGE_HANDLER AUS

Definiert einen Eintrag in einer meldungszuordnung.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>Parameter

*msg*<br/>
[in] Die Windows-Meldung.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

MESSAGE_HANDLER aus ordnet eine Windows-Meldung an die angegebenen Handler-Funktion.

Jede Funktion, die in einem Makro MESSAGE_HANDLER aus angegebenen muss wie folgt definiert werden:

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

Die Zuordnung Nachrichtensätze `bHandled` auf "true", bevor Sie `MessageHandler` aufgerufen wird. Wenn `MessageHandler` ist nicht vollständig verarbeitet die Nachricht sollte `bHandled` auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen meldungszuordnungen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Zusätzlich zu MESSAGE_HANDLER aus, können Sie [COMMAND_HANDLER](#command_handler) und [NOTIFY_HANDLER](#notify_handler) zuordnen [WM_COMMAND](/windows/desktop/menurc/wm-command) und [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachrichten , bzw.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="message_range_handler"></a>  MESSAGE_RANGE_HANDLER

Ähnlich wie [MESSAGE_HANDLER aus](#message_handler), aber die Zuordnungen, die einen Bereich von Windows-zu einer einzelnen Handler-Funktion Meldungen.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>Parameter

*msgFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Nachrichten.

*msgLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Nachrichten.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="notify_code_handler"></a>  NOTIFY_CODE_HANDLER

Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachricht nur anhand der Benachrichtigungscode.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>Parameter

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="notify_handler"></a>  NOTIFY_HANDLER

Definiert einen Eintrag in einer meldungszuordnung.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner des Steuerelements, das Sie die Nachricht gesendet.

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

NOTIFY_HANDLER ordnet eine [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachricht an die angegebenen Handler-Funktion, die auf der Grundlage der Benachrichtigungscode und der Bezeichner des.

Jede Funktion, die in einem Makro NOTIFY_HANDLER angegebenen muss wie folgt definiert werden:

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

Die Zuordnung Nachrichtensätze `bHandled` auf "true", bevor Sie `NotifyHandler` aufgerufen wird. Wenn `NotifyHandler` ist nicht vollständig verarbeitet die Nachricht sollte `bHandled` auf "false", um anzugeben, die Nachricht noch weitere Verarbeitung erforderlich.

> [!NOTE]
>  Beginnen Sie immer eine meldungszuordnung mit [BEGIN_MSG_MAP](#begin_msg_map). Sie können dann mit nachfolgenden alternativen meldungszuordnungen deklarieren [ALT_MSG_MAP](#alt_msg_map). Die [END_MSG_MAP](#end_msg_map) Makro markiert das Ende der nachrichtenzuordnung. Jede nachrichtenzuordnung muss genau eine Instanz des BEGIN_MSG_MAP und END_MSG_MAP haben.

Zusätzlich zu NOTIFY_HANDLER, können Sie [MESSAGE_HANDLER aus](#message_handler) eine WM_NOTIFY-Nachricht ohne Berücksichtigung der einen Bezeichner oder Code zuordnen. In diesem Fall `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` leitet alle WM_NOTIFY-Meldungen zu `OnHandlerFunction`.

Weitere Informationen zur Verwendung von meldungszuordnungen in ATL finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="notify_id_handler"></a>  NOTIFY_ID_HANDLER

Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet eine [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachricht nur auf Grundlage des Steuerelements.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner des Steuerelements, das Sie die Nachricht gesendet.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="notify_range_code_handler"></a>  NOTIFY_RANGE_CODE_HANDLER

Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch ordnet [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachrichten mit einem bestimmten Benachrichtigungscode aus einem Bereich von Steuerelementen zu einer einzelnen Handler-Funktion.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

Dieser Bereich basiert auf den Bezeichner des Steuerelements, das Sie die Nachricht gesendet.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="notify_range_handler"></a>  NOTIFY_RANGE_HANDLER

Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet [WM_NOTIFY](/windows/desktop/controls/wm-notify) Nachrichten aus einem Bereich von Steuerelementen zu einer einzelnen Handler-Funktion.

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="remarks"></a>Hinweise

Dieser Bereich basiert auf den Bezeichner des Steuerelements, das Sie die Nachricht gesendet.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflect_notifications"></a>  REFLECT_NOTIFICATIONS

Gibt Nachrichten zurück an das untergeordnete Fenster (Steuerelement), das sie gesendet wurden.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>Hinweise

Dieses Makro wird als Teil des übergeordneten Fensters meldungszuordnung angeben.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_command_code_handler"></a>  REFLECTED_COMMAND_CODE_HANDLER

Ähnlich wie [COMMAND_CODE_HANDLER](#command_code_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster übernommen.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>Parameter

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_command_handler"></a>  REFLECTED_COMMAND_HANDLER

Ähnlich wie [COMMAND_HANDLER](#command_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster übernommen.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_command_id_handler"></a>  REFLECTED_COMMAND_ID_HANDLER

Ähnlich wie [COMMAND_ID_HANDLER](#command_id_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster übernommen.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_command_range_code_handler"></a>  REFLECTED_COMMAND_RANGE_CODE_HANDLER

Ähnlich wie [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster übernommen.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*Code*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_command_range_handler"></a>  REFLECTED_COMMAND_RANGE_HANDLER

Ähnlich wie [COMMAND_RANGE_HANDLER](#command_range_handler), jedoch ordnet Befehle, die über das übergeordnete Fenster übernommen.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_notify_code_handler"></a>  REFLECTED_NOTIFY_CODE_HANDLER

Ähnlich wie [NOTIFY_CODE_HANDLER](#notify_code_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster übernommen.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>Parameter

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_notify_handler"></a>  REFLECTED_NOTIFY_HANDLER

Ähnlich wie [NOTIFY_HANDLER](#notify_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster übernommen.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_notify_id_handler"></a>  REFLECTED_NOTIFY_ID_HANDLER

Ähnlich wie [NOTIFY_ID_HANDLER](#notify_id_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster übernommen.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Der Bezeichner der dem Menüelement-Steuerelement oder Accelerator.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_notify_range_code_handler"></a>  REFLECTED_NOTIFY_RANGE_CODE_HANDLER

Ähnlich wie [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster übernommen.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*cd*<br/>
[in] Der Benachrichtigungscode.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="reflected_notify_range_handler"></a>  REFLECTED_NOTIFY_RANGE_HANDLER

Ähnlich wie [NOTIFY_RANGE_HANDLER](#notify_range_handler), jedoch ordnet Benachrichtigungen über das übergeordnete Fenster übernommen.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Parameter

*idFirst*<br/>
[in] Markiert den Beginn des einen zusammenhängenden Bereich von Steuerelement-IDs.

*idLast*<br/>
[in] Markiert das Ende einer zusammenhängenden Bereich von Steuerelement-IDs.

*func*<br/>
[in] Der Name der Meldungshandler-Funktion.

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
