---
title: SEGMENT | Microsoft Docs
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
ms.openlocfilehash: c55416cc5a757128c9cc97b2f342953911ac2946
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
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
 **USE16**, **USE32**, **FLATFILE**  
  
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