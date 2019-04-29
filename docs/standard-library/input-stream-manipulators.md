---
title: Eingabestream-Manipulatoren
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 17f18aa127b84538229b3cf4e4246dfefb6c1f98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404909"
---
# <a name="input-stream-manipulators"></a>Eingabestream-Manipulatoren

Viele Manipulatoren, z. B. [Setprecision](../standard-library/iomanip-functions.md#setprecision), werden definiert, für die `ios` Klasse und sind somit für Eingabestreams relevant. Einige Manipulatoren beeinflussen jedoch tatsächlich Eingabestreamobjekte. Für diejenigen, die das tun, sind die Basismanipulatoren `dec`, `oct` und `hex` die Wichtigsten, welche die Konvertierungsbasis festlegen, die Zahlen aus dem Eingabestream verwendet.

Während des Extrahierens ermöglicht der `hex`-Manipulator die Verarbeitung von verschiedenen Eingabeformaten. Zum Beispiel c, C, 0xc, 0xC, 0Xc und 0XC werden alle als die ganze Dezimalzahl 12 interpretiert. Jedes Zeichen außer 0 bis 9, A bis F, a bis f, x und X beendet die numerische Konvertierung. Demnach wird die Sequenz `"124n5"` mit dem festgelegten [basic_ios::fail](../standard-library/basic-ios-class.md#fail)-Bit in die Zahl 124 konvertiert.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
