---
title: ITarget-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 4bd6b21e274431449c8fac452995dd66fc1aef1b
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="itarget-class"></a>ITarget-Klasse
Die `ITarget`-Klasse ist die Schnittstelle für alle Zielblöcke. Zielblöcke nehmen Meldungen auf, die von `ISource`-Blöcken angeboten werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Nutzlast in den Nachrichten vom Zielblock akzeptiert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`filter_method`|Die Signatur einer beliebigen Methode, die von dem Block, der gibt verwendet eine `bool` um zu bestimmen, ob eine bereitgestellte Meldung akzeptiert werden sollen.|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ ITarget-Destruktor](#dtor)|Zerstört das `ITarget`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[weitergeben](#propagate)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Meldung von einem Quellblock an diesen Zielblock.|  
|[Senden](#send)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt eine Nachricht synchron an den Zielblock.|  
|[supports_anonymous_source](#supports_anonymous_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt True oder False, abhängig davon, ob die Nachrichtenblock akzeptiert Nachrichten Angeboten von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode gibt `true`, das Ziel kann eine Nachricht angebotene nicht verschieben, wie die Nutzung des eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in seiner Sourse Link Registrierung identifiziert werden muss.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[link_source](#link_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen angegebenen Quellblock mit diesem `ITarget` Block.|  
|[unlink_source](#unlink_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse Quellblocks einer angegebenen dies `ITarget` Block.|  
|[unlink_sources](#unlink_sources)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Quellblöcke dies `ITarget` Block.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITarget`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a>~ ITarget 

 Zerstört das `ITarget`-Objekt.  
  
```
virtual ~ITarget();
```  
  
##  <a name="link_source"></a>link_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen angegebenen Quellblock mit diesem `ITarget` Block.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Die `ISource` blockieren, der mit dieser verknüpft `ITarget` Block.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke über miteinander verbunden werden sollen die `link_target` Methode `ISource` Blöcke, die aufruft die `link_source` Methode auf dem entsprechenden Ziel.  
  
##  <a name="propagate"></a>weitergeben 

 Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Meldung von einem Quellblock an diesen Zielblock.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder der `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
##  <a name="send"></a>Senden 

 Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt eine Nachricht synchron an den Zielblock.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger für den Quellblock, der die Meldung anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Anzeichen, was das Ziel entschieden, mit der Meldung zu tun.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder der `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
 Mithilfe der `send` Methode außerhalb Nachrichteninitiierung und Weitergabe von Nachrichten innerhalb eines Netzwerks ist gefährlich und kann zu Deadlocks führen.  
  
 Wenn `send` zurückgibt, wurde die Meldung entweder bereits akzeptiert und in den Zielblock übertragen, oder es wurde vom Ziel abgelehnt.  
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt True oder False, abhängig davon, ob die Nachrichtenblock akzeptiert Nachrichten Angeboten von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode gibt `true`, das Ziel kann eine Nachricht angebotene nicht verschieben, wie die Nutzung des eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in seiner Sourse Link Registrierung identifiziert werden muss.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn der Block die Nachricht von einer Quelle annehmen kann, die nicht verknüpft ist `false` andernfalls.  
  
##  <a name="unlink_source"></a>unlink_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse Quellblocks einer angegebenen dies `ITarget` Block.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Die `ISource` Sperren aufgehoben wird, von dieser `ITarget` Block.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke sollten getrennt werden, mithilfe der `unlink_target` oder `unlink_targets` Methoden `ISource` Blöcke, die aufruft die `unlink_source` Methode auf dem entsprechenden Ziel.  
  
##  <a name="unlink_sources"></a>unlink_sources 

 Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Quellblöcke dies `ITarget` Block.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ISource-Klasse](isource-class.md)

