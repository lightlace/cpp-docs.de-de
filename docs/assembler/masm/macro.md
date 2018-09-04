---
title: MAKRO | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MACRO
dev_langs:
- C++
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d957935c9ca91d2d09a093350c8d23a848e58b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688867"
---
# <a name="macro"></a>MACRO

Markiert einen Makro-Block aufgerufen *Namen* und richtet *Parameter* Platzhalter für Argumente zu übergeben, wenn das Makro aufgerufen wird.

## <a name="syntax"></a>Syntax

> *Namen* MAKRO [[*Parameter* [[: REQ |: =*Standard* |: VARARG]]]]...<br/>
> *Anweisungen*<br/>
> ENDM [[*Wert*]]

## <a name="remarks"></a>Hinweise

Funktionsergebnis ist ein Makro *Wert* an die aufrufende Anweisung.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>