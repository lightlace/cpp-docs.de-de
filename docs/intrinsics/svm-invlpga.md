---
title: __svm_invlpga | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __svm_invlpga
dev_langs:
- C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0343222a08b1ab192be733a1f583cc287a9d3377
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="svminvlpga"></a>__svm_invlpga
**Microsoft-spezifisch**  
  
 Erklärt die Zuordnungseintrags Adresse des Computers Übersetzung aussehen-Aside-Puffer. Parameter geben die virtuelle Adresse und die Adresse Raum-ID der Seite, um die für ungültig zu erklären.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `Va`|Die virtuelle Adresse der Seite, um die für ungültig zu erklären.|  
|[in] `ASID`|Die Adresse Speicherplatz Bezeichner (ASID) der Seite, um die für ungültig zu erklären.|  
  
## <a name="remarks"></a>Hinweise  
 Die `__svm_invlpga` -Funktion ist gleichbedeutend mit der `INVLPGA` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593 Revision 3.11, an die [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_invlpga`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)