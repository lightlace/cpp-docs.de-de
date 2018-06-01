---
title: Linkertoolfehler Lnk1309 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1309
dev_langs:
- C++
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffecdc891a9fe0d1c17d6e36c87f5df10b449ec
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704097"
---
# <a name="linker-tools-error-lnk1309"></a>Linkertoolfehler LNK1309

> *Typ1* -Modul gefunden; ungültige mit Option/CLRIMAGETYPE:*Typ2*

## <a name="remarks"></a>Hinweise

Ein CLR-imagetyps wurde angefordert, mit **/CLRIMAGETYPE** , aber der Linker konnte ein Image dieses Typs erzeugen, da eine oder mehrere Module nicht mit diesem Typ kompatibel sind.

LNK1309 wird beispielsweise ausgegeben, wenn Sie angeben, **/CLRIMAGETYPE:safe** und übergeben Sie ein Modul mit erstellten **/CLR: pure**.

Die **/CLR: pure** und **/CLR: safe** Optionen und Support-compilerbibliotheken sind in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Sie sehen auch LNK1309, wenn Sie versuchen, eine teilweise vertrauenswürdige Ptrustu [d] .lib mit reine CLR-Anwendung zu erstellen. Informationen zum Erstellen einer teilweise vertrauenswürdigen Anwendung finden Sie unter [Vorgehensweise: Erstellen einer teilweise vertrauenswürdigen Anwendung durch Entfernen der Abhängigkeit auf der CRT-Bibliothek-DLL](../../dotnet/create-a-partially-trusted-application.md).

Weitere Informationen finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) und [/CLRIMAGETYPE (Angeben der CLR Image-)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).