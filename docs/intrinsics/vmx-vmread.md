---
title: __vmx_vmread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 351ef951a57a4f100861dbd12b8a77d11fc41df8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmread"></a>__vmx_vmread
**Microsoft-spezifisch**  
  
 Liest ein bestimmtes Feld aus der aktuellen virtuellen Maschine Kontrollstruktur (VMCS), und platziert sie in der angegebenen Position.  
  
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
|[in] `Field`|Das zu lesende VMCS-Feld.|  
|[in] `FieldValue`|Ein Zeiger auf den Speicherort zum Speichern des Werts zu lesen, aus dem VMCS Feld gemäß den `Field` Parameter.|  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `__vmx_vmread` -Funktion ist gleichbedeutend mit der `VMREAD` computeranweisung. Der Wert, der die `Field` Parameter ist eine codierte Feldindex, die in der Intel-Dokumentation beschrieben wird. Dokumentieren Sie für Weitere Informationen suchen, für das Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) site, und klicken Sie dann finden Sie in Anhang C dieses Dokuments .  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)