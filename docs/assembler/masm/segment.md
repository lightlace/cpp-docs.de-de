---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: f37be47b92a71e20821cd1e40f8cf1350dfedaff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615422"
---
# <a name="segment"></a>SEGMENT

Definiert ein Programm Segment namens *Namen* müssen der Segment-Attribute

## <a name="syntax"></a>Syntax

> *Namen* SEGMENT [[schreibgeschützt]] [[*ausrichten*]] [[*kombinieren*]] [[*verwenden*]] [[*Merkmale*]] ALIAS (*Zeichenfolge*) [['*Klasse*']]<br/>
> *Anweisungen*<br/>
> *Namen* endet

#### <a name="parameters"></a>Parameter

*align*<br/>
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

*combine*<br/>
**Öffentliche**, **STACK**, **allgemeine**, **Arbeitsspeicher**, **am**<em>Adresse</em>, **PRIVATE**

*Verwendung*<br/>
**USE16**, **USE32**, **FLATFILE**

*Merkmale*<br/>
**INFO**, **lesen**, **schreiben**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, und **verwerfen**

Diese werden nur für COFF-Format unterstützt, und die Merkmale für COFF-Abschnitt von ähnlichen Namen entsprechen (z. B. **SHARED** IMAGE_SCN_MEM_SHARED entspricht). Lesen legt das Flag IMAGE_SCN_MEM_READ fest. Das veraltete READONLY-Flag verursacht Abschnitt, um die IMG_SCN_MEM_WRITE-Flag zu deaktivieren. Wenn alle *Merkmale* festgelegt sind, werden die Standardeigenschaften nicht verwendet werden und nur die Programmierer angegebenen Flags sind gültig.

`ALIAS(` *Zeichenfolge* `)`<br/>
Diese Zeichenfolge wird als der Name des Abschnitts in der ausgegebenen COFF-Objekt verwendet.  Erstellt mehrere Abschnitte mit den gleichen externen Namen mit unterschiedlichen Namen von MASM-Segment an.

Nicht unterstützt, die mit **"/ OMF"**.

*class*<br/>
Legt fest, wie Segmente kombiniert und in der Datei assemblierten sortiert werden. Typische Werte sind, `'DATA'`, `'CODE'`, `'CONST'` und `'STACK'`

## <a name="remarks"></a>Hinweise

Für `ALIGN(n)`, *n* kann eine beliebige Potenz von 2 zwischen 1 und 8192 sein; nicht unterstützt wird, mit **"/ OMF"**.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>