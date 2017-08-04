---
title: "ANSI C-Kompatibilität | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Ansi
dev_langs:
- C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 7e6c5d4045f0b71890a34d845b898844ca550ca8
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="ansi-c-compliance"></a>ANSI C-Kompatibilität
Die Namenskonvention für alle Microsoft-spezifischen Bezeichner im Laufzeitsystem (z.B. Funktionen, Makros, Konstanten, Variablen und Typdefinitionen) ist ANSI-kompatibel. In dieser Dokumentation wird jede Laufzeitfunktion, die den Standards ANSI/ISO C entspricht, als ANSI-kompatibel aufgeführt. ANSI-kompatible Anwendungen sollten nur diese ANSI-kompatiblen Funktionen verwenden.  
  
 Die Namen der Microsoft-spezifischen Funktionen und globalen Variablen beginnen mit einem einzelnen Unterstrich. Diese Namen können nur lokal innerhalb des Bereichs Ihres Codes überschrieben werden. Wenn Sie z.B. die Microsoft-Laufzeitheaderdateien einbeziehen, können Sie weiterhin die Microsoft-spezifische Funktion `_open` lokal überschreiben, indem Sie eine lokale Variable mit demselben Namen deklarieren. Allerdings können Sie diesen Namen nicht für Ihre eigene globale Funktion oder globale Variable verwenden.  
  
 Die Namen von Microsoft-spezifischen Makros und Manifestkonstanten beginnen mit zwei Unterstrichen oder einem einzelnen vorangestellten Unterstrich, direkt gefolgt von einem Großbuchstaben. Der Bereich dieser Bezeichner ist absolut. Sie können aus diesem Grund beispielsweise nicht den Microsoft-spezifischen Bezeichner **_UPPER** verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)
