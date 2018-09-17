---
title: __writeeflags | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writeeflags
dev_langs:
- C++
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c01e10a77278f0a02658778ec178f0a4226eb36
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704859"
---
# <a name="writeeflags"></a>__writeeflags
Schreibt den angegebenen Wert in das Programm Status und -Steuerelement (EFLAGS) zu registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*Wert*|[in] Der Wert, der registriert wird, EFLAGS geschrieben werden soll. Die `Value` Parameter ist 32 Bits lang für eine 32-Bit-Plattform und 64 Bit lang für eine 64-Bit-Plattform.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__writeeflags`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)