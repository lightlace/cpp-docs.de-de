---
title: SEGMENT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 253c3b389bd0411e6b5096e914b6a844c8f40805
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="segment"></a>SEGMENT
Definiert ein Programm Segment bezeichnet *Namen* bei Segment-Attributen  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>Parameter  
 *align*  
 Der Bereich der Speicheradressen, die von denen eine Startadresse für das Segment ausgewählt werden kann. Die Ausrichtungstyp kann eines der folgenden sein:  
  
|Ausrichten von Typ|Startadresse|  
|----------------|----------------------|  
|**BYTE**|Adresse des nächsten verfügbaren Byte.|  
|**WORD**|Nächste verfügbare Word-Adresse (2 Bytes pro Wort).|  
|**DWORD**|Nächste verfügbare Doppelwort-Adresse (4 Byte pro Doppelwort).|  
|**PARA**|Nächste verfügbare Absatz Adresse (16 Bytes pro Absatz).|  
|**PAGE**|Nächste verfügbare Adresse (256 Byte pro Seite).|  
|**Richten Sie**(*n*)|Nächste verfügbare *n*th-Byte-Adresse. Weitere Informationen finden Sie unter "Hinweise" Abschnitt.|  
  
 Wenn dieser Parameter nicht angegeben wird, **Absatz** wird standardmäßig verwendet.  
  
 *combine*  
 **Öffentliche**, **Stapel**, **allgemeine**, **Arbeitsspeicher**, **am *** Adresse*, **PRIVATE**  
  
 *Verwendung*  
 **USE16**, **USE32**, **FLAT**  
  
 `characteristics`  
 **INFO**, **lesen**, **schreiben**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, und **verwerfen**  
  
 Diese werden nur für COFF unterstützt und die Merkmale des COFF-Abschnitt des ähnlichen Namen entsprechen (z. B. **SHARED** IMAGE_SCN_MEM_SHARED entspricht). Lesen legt das Flag IMAGE_SCN_MEM_READ fest. Die veraltete READONLY-Flag verursacht Abschnitt, um das IMG_SCN_MEM_WRITE-Flag zu deaktivieren. Wenn `characteristics` festgelegt sind, wird die Standardeigenschaften werden nicht verwendet und nur die vom Programmierer angegebenen Flags sind immer wirksam.  
  
 `ALIAS(` `string` `)`  
 Diese Zeichenfolge wird als der Name des Abschnitts in der ausgegebenen COFF-Objekt verwendet.  Erstellt mehrere Abschnitte mit den gleichen externen Namen mit unterschiedlichen MASM-Segmentnamen.  
  
 Nicht unterstützt, die mit **/OMF**.  
  
 `class`  
 Legt fest, wie Segmente kombiniert und in der Datei assemblierten sortiert werden soll. Typische Werte sind, `'DATA'`, `'CODE'`, `'CONST'` und `'STACK'`  
  
## <a name="remarks"></a>Hinweise  
 Für `ALIGN(n)`, `n` möglicherweise Potenz von 2 von 1 auf 8192; nicht unterstützt, mit **/OMF**.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)