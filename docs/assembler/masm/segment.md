---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: b7344d9cb685e0212748d7835e19f398f14979e7
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74393731"
---
# <a name="segment"></a>SEGMENT

Definiert ein Programm Segment namens " *Name* " mit Segment Attributen.

## <a name="syntax"></a>Syntax

> *namens* **Segment** ⟦**Schreib**geschützt ⟧ ⟦*align*⟧ ⟦ ⟧*kombinieren*⟦ ⟧*use*⟦ ⟧*Characteristics*⟦ **Alias (** _String_ **)** ⟧ __'__ *Class* __'__ \
> *Anweisungen*\
> *Name* **endet**

#### <a name="parameters"></a>Parameter

*align*<br/>
Der Bereich der Speicheradressen, von dem eine Startadresse für das Segment ausgewählt werden kann. Der Ausrichtungstyp kann eine der folgenden sein:

|Typ ausrichten|Startadresse|
|----------------|----------------------|
|**BYTE**|Nächste verfügbare Byte Adresse.|
|**WORD**|Nächste verfügbare Wort Adresse (2 Bytes pro Wort).|
|**DWORD**|Nächste verfügbare doppelte Wort Adresse (4 Bytes pro doppeltes Wort).|
|**Abs**|Nächste verfügbare Absatz Adresse (16 Byte pro Absatz).|
|**PAGE**|Nächste verfügbare Seitenadresse (256 Byte pro Seite).|
|**Ausrichten**(*n*)|Nächste verfügbare *n*-te Byte Adresse. Weitere Informationen finden Sie im Abschnitt "Hinweise".|

Wenn dieser Parameter nicht angegeben wird, wird standardmäßig **para** verwendet.

*kombinieren*\
**Public**, **Stack**, **Common**, **Memory**, **at**<em>Address</em>, **private**

\ *verwenden*
**USE16**, **USE32**, **Flat**

*Eigenschaften*\
**Info**, **Lesen**, **Schreiben**, **Ausführen**, **Shared**, **NOPAGE**, **NoCache**und **verwerfen**

Diese werden nur für COFF unterstützt und entsprechen den COFF-Abschnitts Merkmalen ähnlichen Namens (" **Shared** " entspricht z. b. IMAGE_SCN_MEM_SHARED). Read legt das IMAGE_SCN_MEM_READ-Flag fest. Das veraltete schreibgeschützte Flag hat bewirkt, dass der Abschnitt das IMG_SCN_MEM_WRITE-Flag gelöscht hat. Wenn *Eigenschaften* festgelegt sind, werden die Standardeigenschaften nicht verwendet, und nur die vom Programmierer angegebenen Flags sind wirksam.

_string_\
Diese Zeichenfolge wird als Abschnitts Name im ausgegebenen COFF-Objekt verwendet.  Erstellt mehrere Abschnitte mit dem gleichen externen Namen und unterschiedlichen MASM-Segment Namen.

Wird bei **/OMF**nicht unterstützt.

*Klasse*\
Gibt an, wie Segmente in der assemblierten Datei kombiniert und angeordnet werden sollen. Typische Werte sind, `'DATA'`, `'CODE'`, `'CONST'` und `'STACK'`

## <a name="remarks"></a>Hinweise

Bei `ALIGN(n)`kann *n* eine beliebige Potenz von 2 zwischen 1 und 8192 sein. wird bei **/OMF**nicht unterstützt.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
