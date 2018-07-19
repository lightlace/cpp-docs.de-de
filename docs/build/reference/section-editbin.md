---
title: -SECTION (EDITBIN) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e29e258b4fb661cfa06e057704bba983ad924f34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378352"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option ändert die Attribute eines Abschnitts, überschreiben die Attribute, die bei die Objektdatei für den Abschnitt kompiliert bzw. verknüpft wurde festgelegt wurden.  
  
 Nach dem Doppelpunkt ( **:** ), geben Sie die *Namen* des Abschnitts. Um den Namen des Abschnitts zu ändern, führen Sie *Namen* mit einem Gleichheitszeichen (=) und ein *Newname* für den Abschnitt.  
  
 Festlegen oder ändern im Abschnitts `attributes`, geben Sie ein Komma (**,**) gefolgt von einem oder mehreren Attributzeichen. Stellen Sie das Zeichen mit einem Ausrufezeichen (!) voran, um ein Attribut zu negieren. Die folgenden Zeichen werden Arbeitsspeicher-Attribute angeben:  
  
|Attribut|Einstellung|  
|---------------|-------------|  
|c|Code|  
|T|Entfernbar|  
|e|executable|  
|i|initialisierte Daten|  
|c|zwischengespeicherte virtuellen Arbeitsspeicher|  
|m|Link zu entfernen|  
|o|Link-Informationen|  
|d|ausgelagerter virtueller Arbeitsspeicher|  
|b|Lesen|  
|s|Freigegeben|  
|n|nicht initialisierte Daten|  
|m|Schreiben|  
  
 Um zu steuern *Ausrichtung*, geben Sie das Zeichen **ein** gefolgt von einem der folgenden Zeichen enthalten, um die Größe der Ausrichtung in Bytes, der wie folgt festlegen:  
  
|Zeichen|Ausrichtungsgröße in bytes|  
|---------------|-----------------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|d|16|  
|t|32|  
|s|64|  
|w|keine Ausrichtung|  
  
 Geben Sie die `attributes` und *Ausrichtung* Zeichen als Zeichenfolge, wobei keine Leerzeichen. Die Zeichen sind nicht in der Groß-/Kleinschreibung beachtet.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)