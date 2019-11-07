---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 853bc9cd22d866357a4cd2d695beccc3efc20acf
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703967"
---
# <a name="invoke-32-bit-masm"></a>Aufrufen (32-Bit-MASM)

Ruft die Prozedur bei der von *Ausdruck*angegebenen Adresse auf und übergibt die Argumente auf dem Stapel oder in Registern gemäß den Standard Aufruf Konventionen des sprach Typs. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> Aufruf *Ausdruck* [[, *Argumente*]]

## <a name="remarks"></a>Hinweise

Jedes Argument, das an die Prozedur übermittelt wird, kann ein Ausdruck, ein Registrierungs Paar oder ein Adress Ausdruck sein (ein Ausdruck, dem `ADDR`vorangestellt ist).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>