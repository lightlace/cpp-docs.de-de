---
title: CAtlAutoThreadModuleT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebf3ba07ac5608a47f4e2bbbe853cb37c033e5f7
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757614"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT-Klasse

Diese Klasse stellt Methoden zum Implementieren eines COM-Servers in einem Thread-Pool, Apartment-Modell.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>Parameter

*T*  
Die Klasse, die die COM-Server implementiert werden.

*ThreadAllocator*  
Die Verwaltung von threadauswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

*dwWait*  
Gibt das Timeoutintervall in Millisekunden an. Der Standardwert ist INFINITE, der Timeoutintervall der Methode nie bedeutet, abgelaufen ist dass.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Diese statischen Funktion wird dynamisch berechnet, und gibt die maximale Anzahl von Threads für die EXE-Modul, das basierend auf der Anzahl der Prozessoren.|

## <a name="remarks"></a>Hinweise

Die Klasse [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) leitet sich von `CAtlAutoThreadModuleT` um ein COM-Server in einem Thread-Pool, Apartment-Modell zu implementieren. Er ersetzt die veraltete Klasse [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

> [!NOTE]
>  Diese Klasse sollte nicht in eine DLL verwendet werden, als Standard *DwWait* Wert INFINITE wird einen Deadlock verursachen, wenn die DLL entladen wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads

Diese statischen Funktion wird dynamisch berechnet, und gibt die maximale Anzahl von Threads für die EXE-Modul, das basierend auf der Anzahl der Prozessoren.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Threads im Modul exe-Datei erstellt werden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie eine andere Methode verwenden, für die Anzahl der Threads berechnen möchten. Standardmäßig ist die Anzahl der Prozessoren die Anzahl der Threads abhängig.

## <a name="see-also"></a>Siehe auch

[IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)   
[IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
[Modulklassen](../../atl/atl-module-classes.md)
