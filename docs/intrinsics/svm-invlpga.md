---
title: __svm_invlpga | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_invlpga
dev_langs: C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 337bca0c446faa36b54e2b033f503f21db4af71d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 Die `__svm_invlpga` -Funktion ist gleichbedeutend mit der `INVLPGA` computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Weitere Informationen zu suchen, für das Dokument "AMD64 Architecture Programmers manuelle Volume 2: System-Programmierung" Dokumentnummer 24593 Revision 3.11, an die [AMD Corporation](http://go.microsoft.com/fwlink/?LinkId=23746) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__svm_invlpga`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)