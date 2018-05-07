---
title: __writeeflags | Microsoft Docs
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
ms.openlocfilehash: 2a2885f2ea103ad43535b11c526b96ed42de45fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="writeeflags"></a>__writeeflags
Schreibt den angegebenen Wert in das Programm Status und -Steuerelement (EFLAGS) registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `Value`|Der Wert, in dem Register EFLAGS zu schreiben. Die `Value` Parameter ist 32 Bits lang für eine 32-Bit-Plattform und 64 Bit lang für eine 64-Bit-Plattform.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__writeeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)