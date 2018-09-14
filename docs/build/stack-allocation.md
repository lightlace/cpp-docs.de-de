---
title: Stack Allocation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098e51f2-eda6-40d0-b149-0b618aa48b47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22c2afae3678e945678862059034b4d60be456b0
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "32380601"
---
# <a name="stack-allocation"></a>Stapelreservierung
Der Prolog einer Funktion ist verantwortlich für die Zuordnung der Stapelspeicher für lokale Variablen, Stapelparameter gespeicherte Register, und registrieren Sie die Parameter.  
  
 Der Bereich ist immer am unteren Rand der Stapel, (selbst wenn Alloca verwendet wird), sodass es immer an die Rücksendeadresse bei einem beliebigen Funktionsaufruf aneinander angrenzen. Mindestens vier Einträge enthält, aber immer ausreichend Speicherplatz für alle Parameter benötigt, von jeder Funktion, die aufgerufen werden kann. Beachten Sie, dass immer Speicherplatz für die Registerparameter, zugewiesen ist, selbst wenn die die Parametern selbst nie auf den Stapel befinden; eine aufgerufene Funktion ist garantiert, dass Speicherplatz für alle seine Parameter zugeordnet wurde. Privatadressen sind für die Registerargumente erforderlich, damit ein zusammenhängender Bereich verfügbar ist, für den Fall, dass die aufgerufene Funktion die Adresse der Argumentliste (Va_list) oder ein einzelnes Argument verwenden muss. Dieser Bereich bietet auch einen praktischer Ort für die Registerargumente während der Ausführung der Thunk sowie eine Option für das Debuggen zu speichern (z. B. die Argumente auf einfache Weise zu suchen, die während des Debuggens, wenn sie an ihrer Basisadresse im Prologcode gespeichert sind). Auch wenn die aufgerufene Funktion über weniger als 4 Parameter verfügt, diese 4-Stack-Standorte gehören effektiv von der aufgerufenen Funktion und können von der aufgerufenen Funktion für andere Zwecke neben Speichern verwendet werden.  Der Aufrufer kann daher keine Informationen in dieser Region des Stapels über einen Funktionsaufruf hinweg speichern.  
  
 Wenn Speicherplatz dynamisch (Alloca) in einer Funktion zugeordnet ist, klicken Sie dann ein nicht flüchtiges Register muss als Frame-Pointer verwendet werden, um die Basis der fester Bestandteil des Stapels zu markieren und diese Register gespeichert werden muss, und im Prolog initialisiert. Beachten Sie, dass wenn Alloca verwendet wird, Aufrufe an den gleichen aufgerufenen vom gleichen Aufrufer unterschiedliche Basisadressen für ihre Parameter registrieren können.  
  
 Der Stapel werden immer 16-Byte-beibehalten, außer im Prolog (z. B., nachdem die Rückgabeadresse mithilfe von Push übertragen wird) und mit Ausnahme der wie angegeben in [Funktionstypen](../build/function-types.md) für eine bestimmte Klasse von Frame-Funktionen.  
  
 Im folgenden finden, dass ein Beispiel für die where-Funktionsaufrufe ein ein innerer Prolog der Funktion Funktion Stapellayout bereits Speicherplatz für alle Register und Stack erforderlichen Parameter B am unteren Rand der Stapel reserviert hat. Der Aufruf wird die Rückgabeadresse und B Prolog reserviert Speicherplatz für die zugehörigen lokalen Variablen, nicht flüchtigen Register und des erforderlichen Speicherplatzes für Funktionen aufrufen. Wenn B Alloca verwendet wird, wird der Platz zwischen der lokalen Variable/permanenten Register und den Eingabeaufforderungsbereich für Parameter Stapel zugeordnet.  
  
 ![AMD-Konvertierungsbeispiel](../build/media/vcamd_conv_ex_5.png "vcAmd_conv_ex_5")  
  
 Wenn die Funktion B eine andere Funktion aufruft, wird die Absenderadresse für RCX direkt unterhalb der Privatadresse abgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)