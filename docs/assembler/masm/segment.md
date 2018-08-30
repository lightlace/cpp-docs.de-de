---
title: SEGMENT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5defce11b611f23b67e5e44ac1b9d406f73c0ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210418"
---
# <a name="segment"></a>SEGMENT
Definiert ein Programm Segment namens *Namen* müssen der Segment-Attribute  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>Parameter  
 *align*  
 Der Bereich der Speicheradressen, die von denen die Startadresse für das Segment ausgewählt werden kann. Der Ausrichtungstyp kann eine der folgenden sein:  
  
|Typ ausrichten|Startadresse|  
|----------------|----------------------|  
|**BYTE**|Adresse des nächsten verfügbaren Byte.|  
|**WORD**|Nächste verfügbare Word-Adresse (2 Byte pro Wort).|  
|**DWORD**|Nächste verfügbare Doppelwort-Adresse (4 Bytes pro Doppelwort).|  
|**PARA**|Nächste verfügbare Absatz-Adresse (16 Bytes pro Absatz).|  
|**PAGE**|Nächste verfügbare Adresse (256 Byte pro Seite).|  
|**AUSRICHTEN**(*n*)|Nächste verfügbare *n*th-Byte-Adresse. Weitere Informationen finden Sie unter "Hinweise" Abschnitt.|  
  
 Wenn dieser Parameter nicht angegeben ist, **PARA** wird standardmäßig verwendet.  
  
 *combine*  
 **Öffentliche**, **STACK**, **allgemeine**, **Arbeitsspeicher**, **am**<em>Adresse</em>, **PRIVATE**  
  
 *Verwendung*  
 **USE16**, **USE32**, **FLATFILE**  
  
 `characteristics`  
 **INFO**, **lesen**, **schreiben**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, und **verwerfen**  
  
 Diese werden nur für COFF-Format unterstützt, und die Merkmale für COFF-Abschnitt von ähnlichen Namen entsprechen (z. B. **SHARED** IMAGE_SCN_MEM_SHARED entspricht). Lesen legt das Flag IMAGE_SCN_MEM_READ fest. Das veraltete READONLY-Flag verursacht Abschnitt, um die IMG_SCN_MEM_WRITE-Flag zu deaktivieren. Wenn alle `characteristics` festgelegt sind, werden die Standardeigenschaften nicht verwendet werden und nur die Programmierer angegebenen Flags sind gültig.  
  
 `ALIAS(` `string` `)`  
 Diese Zeichenfolge wird als der Name des Abschnitts in der ausgegebenen COFF-Objekt verwendet.  Erstellt mehrere Abschnitte mit den gleichen externen Namen mit unterschiedlichen Namen von MASM-Segment an.  
  
 Nicht unterstützt, die mit **"/ OMF"**.  
  
 `class`  
 Legt fest, wie Segmente kombiniert und in der Datei assemblierten sortiert werden. Typische Werte sind, `'DATA'`, `'CODE'`, `'CONST'` und `'STACK'`  
  
## <a name="remarks"></a>Hinweise  
 Für `ALIGN(n)`, `n` kann eine beliebige Potenz von 2 zwischen 1 und 8192 sein; nicht unterstützt wird, mit **"/ OMF"**.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)