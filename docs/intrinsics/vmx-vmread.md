---
title: __vmx_vmread | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0c8b5a22cfef8ebde74fbe6d1f6920a969e7bc6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706380"
---
# <a name="vmxvmread"></a>__vmx_vmread
**Microsoft-spezifisch**  
  
 Liest ein bestimmtes Feld aus der aktuellen VM-Steuerelement-Struktur (VMCS), und platziert sie in der angegebenen Position.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*Feld*|[in] Das zu lesende VMCS-Feld.|  
|*FieldValue*|[in] Ein Zeiger auf den Speicherort zum Speichern des Werts zu lesen, aus dem vom angegebenen VMCS-Feld der `Field` Parameter.|  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `__vmx_vmread` -Funktion ist gleichbedeutend mit der `VMREAD` computeranweisung. Der Wert des der `Field` -Parameter ist eine codierte Feldindex, die in der Intel-Dokumentation beschrieben ist. Dokumentieren Sie weitere Informationen suchen Sie nach dem Dokument "Intel Virtualization Technical Specification for the IA-32 Intel Architecture," Dokumentnummer C97063-002 auf der [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm) Standort aus, und klicken Sie dann finden Sie in Anhang C des Dokuments .  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmread`|x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)