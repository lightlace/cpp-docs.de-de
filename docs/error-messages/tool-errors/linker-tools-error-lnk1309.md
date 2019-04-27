---
title: Linkertoolfehler LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: ea675ca835dfc3fe4881e5fabbea746a4442b10a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187442"
---
# <a name="linker-tools-error-lnk1309"></a>Linkertoolfehler LNK1309

> *type1* -Modul gefunden; ungültig mit Schalter, / CLRIMAGETYPE:*Typ2*

## <a name="remarks"></a>Hinweise

Eine CLR-Imagetyp wurde mit angefordert **/CLRIMAGETYPE** , aber der Linker konnte ein Abbild dieses Typs erzeugen, da ein oder mehrere Module nicht mit diesem Typ kompatibel waren.

LNK1309 wird beispielsweise ausgegeben, wenn Sie angeben, **Safe** und übergeben Sie ein Modul mit erstellten **/CLR: pure**.

Die **/CLR: pure** und **/CLR: safe** Compiler-Optionen und Support-Bibliotheken sind in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Sie können LNK1309 werden auch angezeigt, wenn Sie versuchen, eine teilweise vertrauenswürdige Ptrustu [d]-LIB mit reine CLR-Anwendung zu erstellen. Informationen zum Erstellen einer teilweise vertrauenswürdigen Anwendung finden Sie unter [Vorgehensweise: Erstellen Sie eine teilweise vertrauenswürdige Anwendung durch Entfernen der Abhängigkeit der CRT-Bibliotheks-DLL](../../dotnet/create-a-partially-trusted-application.md).

Weitere Informationen finden Sie unter [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [/CLRIMAGETYPE (Typ der CLR-Images angeben)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).