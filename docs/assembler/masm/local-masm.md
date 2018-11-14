---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327602"
---
# <a name="local-masm"></a>LOCAL (MASM)

In der ersten Anweisung, innerhalb eines Makros **lokalen** definiert, die für jede Instanz des Makros eindeutig sind.

## <a name="syntax"></a>Syntax

> LOKALE *Localname* \[, *Localname*]...
>
> LOKALE *Bezeichnung* \[ __\[__ *Anzahl*__]__ ] \[ __:__  *Typ*] \[ __,__ *Bezeichnung* \[ __\[__ *Anzahl* __]__  ] \[ *Typ*]]...

## <a name="remarks"></a>Hinweise

In der zweiten Anweisung, in der Definition einer Prozedur (**PROC**), **lokalen** erstellt stapelbasierten Variablen, die für die Dauer der Prozedur vorhanden sind. Die *Bezeichnung* möglicherweise als einfache Variable oder ein Array mit *Anzahl* Elemente.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>