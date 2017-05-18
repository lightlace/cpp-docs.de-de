---
title: Klasse Win32ThreadTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
caps.latest.revision: 20
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: fa331e05d647b5e2b9a0a76581e75d6b40366f95
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits-Klasse
Diese Klasse stellt die Funktion für ein Windows-Thread. Verwenden Sie diese Klasse, wenn der Thread keine CRT-Funktionen verwenden möchten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Statisch) Rufen Sie diese Funktion, um einen Thread zu erstellen, der keine CRT-Funktionen verwenden sollten.|  
  
## <a name="remarks"></a>Hinweise  
 Thread-Merkmale sind Klassen, die eine Funktion für einen bestimmten Thread zu ermöglichen. Die Funktion verfügt über die gleiche Signatur und Semantik wie die Windows- [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Funktion.  
  
 Thread-Merkmale werden durch die folgenden Klassen verwendet:  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Wenn der Thread CRT-Funktionen verwenden, verwenden Sie [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="createthread"></a>Win32ThreadTraits::CreateThread  
 Rufen Sie diese Funktion, um einen Thread zu erstellen, der keine CRT-Funktionen verwenden sollten.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpsa`  
 Die Sicherheitsattribute für den neuen Thread.  
  
 `dwStackSize`  
 Die Stapelgröße für den neuen Thread.  
  
 `pfnThreadProc`  
 Die Threadprozedur des neuen Threads.  
  
 `pvParam`  
 Der Parameter an die Threadprozedur übergeben werden.  
  
 `dwCreationFlags`  
 Die Erstellung flags (0 oder CREATE_SUSPENDED).  
  
 `pdwThreadId`  
 [out] Die Adresse der DWORD-Variablen, die bei Erfolg die Thread-ID des neu erstellten Threads empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für den neu erstellten Thread oder NULL bei einem Fehler zurück. Rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um erweiterte Fehlerinformationen abzurufen.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Weitere Informationen über die Parameter dieser Funktion.  
  
 Diese Funktion ruft `CreateThread` auf den Thread zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

