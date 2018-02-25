---
title: ITarget-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04c0750c6a33756ca2fe207c4c4066a5b5b8da96
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`filter_method`|Die Signatur einer beliebigen Methode, die vom Block, der zurückgibt verwendet eine `bool` um zu bestimmen, ob eine angebotene Nachricht akzeptiert werden sollen.|  
|`type`|Ein Typalias für `T`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ ITarget-Destruktor](#dtor)|Zerstört das `ITarget`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[propagate](#propagate)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Nachricht von ein Quellblock an diesen Zielblock.|  
|[Senden](#send)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt synchron eine Meldung an den Zielblock.|  
|[supports_anonymous_source](#supports_anonymous_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt "true" oder "false", je nachdem, ob der Nachrichtenblock akzeptiert Nachrichten angeboten, die von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode zurückgibt `true`, das Ziel kann nicht als Verbrauch von eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in die Registrierung seiner Sourse Link identifiziert werden, muss eine angebotene Nachricht zu verschieben.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[link_source](#link_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen angegebenen Quellblock mit diesem `ITarget` Block.|  
|[unlink_source](#unlink_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einer angegebenen Quellblock aus diesem `ITarget` Block.|  
|[unlink_sources](#unlink_sources)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung von diesem alle Quellblöcke `ITarget` Block.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITarget`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a> ~ITarget 

 Zerstört das `ITarget`-Objekt.  
  
```
virtual ~ITarget();
```  
  
##  <a name="link_source"></a> link_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse verknüpft einen angegebenen Quellblock mit diesem `ITarget` Block.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Die `ISource` blockieren, um dies zu verknüpfenden `ITarget` Block.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke über miteinander verbunden werden soll die `link_target` Methode auf `ISource` -Blöcken, die aufgerufen wird, werden die `link_source` Methode auf dem entsprechenden Ziel.  
  
##  <a name="propagate"></a> weitergeben 

 Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Nachricht von ein Quellblock an diesen Zielblock.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger auf der Quellblock die Nachricht anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
##  <a name="send"></a> Senden 

 Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt synchron eine Meldung an den Zielblock.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PMessage`  
 Ein Zeiger auf das `message`-Objekt.  
  
 `_PSource`  
 Ein Zeiger auf der Quellblock die Nachricht anbietet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, mit der Nachricht geschehen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter ist `NULL`.  
  
 Mithilfe der `send` Methode außerhalb Nachrichteninitiierung und zur Weitergabe von Nachrichten innerhalb eines Netzwerks ist riskant und kann zu Deadlocks führen.  
  
 Wenn `send` zurückgibt, wurde die Nachricht entweder bereits akzeptiert und an den Zielblock übertragen, oder es wurde vom Ziel abgelehnt.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse gibt "true" oder "false", je nachdem, ob der Nachrichtenblock akzeptiert Nachrichten angeboten, die von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode zurückgibt `true`, das Ziel kann nicht als Verbrauch von eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in die Registrierung seiner Sourse Link identifiziert werden, muss eine angebotene Nachricht zu verschieben.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der Block Nachricht aus einer Quelle annehmen kann, die nicht verknüpft ist `false` andernfalls.  
  
##  <a name="unlink_source"></a> unlink_source 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einer angegebenen Quellblock aus diesem `ITarget` Block.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_PSource`  
 Die `ISource` Sperren aufgehoben wird, von diesem `ITarget` Block.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke sollten getrennt werden, mithilfe der `unlink_target` oder `unlink_targets` Methoden auf `ISource` -Blöcken, die aufgerufen werden die `unlink_source` Methode auf dem entsprechenden Ziel.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung von diesem alle Quellblöcke `ITarget` Block.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ISource-Klasse](isource-class.md)
