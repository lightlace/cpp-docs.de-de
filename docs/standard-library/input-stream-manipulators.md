---
title: Eingabestream-Manipulatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30f642dc4942491bd73265e3d647d3281f97c1e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="input-stream-manipulators"></a>Eingabestream-Manipulatoren

Viele Manipulatoren wie z. B. [Setprecision](../standard-library/iomanip-functions.md#setprecision), definiert sind, für die `ios` Klasse, und daher Streams Eingabespalten gelten. Einige Manipulatoren beeinflussen jedoch tatsächlich Eingabestreamobjekte. Für diejenigen, die das tun, sind die Basismanipulatoren `dec`, `oct` und `hex` die Wichtigsten, welche die Konvertierungsbasis festlegen, die Zahlen aus dem Eingabestream verwendet.

Während des Extrahierens ermöglicht der `hex`-Manipulator die Verarbeitung von verschiedenen Eingabeformaten. Zum Beispiel c, C, 0xc, 0xC, 0Xc und 0XC werden alle als die ganze Dezimalzahl 12 interpretiert. Jedes Zeichen außer 0 bis 9, A bis F, a bis f, x und X beendet die numerische Konvertierung. Demnach wird die Sequenz `"124n5"` mit dem festgelegten [basic_ios::fail](../standard-library/basic-ios-class.md#fail)-Bit in die Zahl 124 konvertiert.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
