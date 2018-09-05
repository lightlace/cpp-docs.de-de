---
title: RUFEN SIE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5698acf9986903a1d6d731c1047484a0ce6904
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676516"
---
# <a name="invoke"></a>INVOKE

Ruft die Prozedur unter der Adresse, die vom *Ausdruck*, wobei die Argumente übergeben werden, auf dem Stapel oder in Registern gemäß den Konventionen für den standard Aufrufen des Typs Language.

## <a name="syntax"></a>Syntax

> INVOKE *Ausdruck* [[, *Argumente*]]

## <a name="remarks"></a>Hinweise

Jedes Argument an die Prozedur übergeben möglicherweise einen Ausdruck, ein paar registrieren oder einen Adressausdruck (ein Ausdruck vorangestellt `ADDR`).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>