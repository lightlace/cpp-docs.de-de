---
title: Linkertoolfehler LNK1112
ms.date: 11/04/2016
f1_keywords:
- LNK1112
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
ms.openlocfilehash: bc01d56fb8144d23b91c82a7f791a70a5dadb7ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607089"
---
# <a name="linker-tools-error-lnk1112"></a>Linkertoolfehler LNK1112

> Modul-Computertyp "*type1*"steht in Konflikt mit dem Zielcomputertyp"*Typ2*"

## <a name="remarks"></a>Hinweise

Die als Eingabe festgelegten Objektdateien wurden für unterschiedliche Computertypen kompiliert.

Wenn Sie z. B. versuchen, eine mit **/clr** und eine mit **/clr:pure** kompilierte Objektdatei (Computertyp CEE) zu verknüpfen, generiert der Linker den Fehler LNK1112. Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Auf ähnliche Weise bei der Erstellung von einem Modul mit dem X64 Compiler und ein anderes Modul mit dem X86 Compiler, und versuchen Sie es, diese zu verknüpfen der Linker Fehler LNK1112 generiert.

Eine mögliche Ursache für diesen Fehler ist, dass Sie eine 64-Bit-Anwendung entwickeln, aber keiner der 64-Bit-Compiler von Visual C++ installiert ist. In diesem Fall stehen die 64-Bit-Konfigurationen nicht zur Verfügung. Um dieses Problem zu beheben, führen Sie das Installationsprogramm für Visual Studio aus und installieren die fehlenden Komponenten von C++.

Dieser Fehler kann auch auftreten, wenn Sie die **aktive Projektmappenkonfiguration** im **Konfigurations-Manager** ändern und anschließend versuchen, das Projekt zu erstellen, bevor Sie die Zwischenprojektdateien gelöscht haben. Wählen Sie zum Beheben dieses Fehlers **Projektmappe neu erstellen** aus dem Menü **Erstellen** aus. Sie können auch **Projektmappe bereinigen** aus dem Menü **Erstellen** auswählen und die Projektmappe anschließend erstellen.

## <a name="see-also"></a>Siehe auch

- [Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
