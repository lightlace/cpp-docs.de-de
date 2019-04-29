---
title: /SECTION (EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 8bcc925b34118630c872a0147b93291626b7c19b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318601"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>Hinweise

Diese Option ändert die Attribute eines Abschnitts, überschreiben die Attribute, die festgelegt wurden, wenn die Objektdatei für den Abschnitt kompiliert bzw. verknüpft wurde.

Nach dem Doppelpunkt ( **:** ), geben Sie die *Namen* des Abschnitts. Um den Namen des Abschnitts zu ändern, führen Sie *Namen* mit einem Gleichheitszeichen (=) und ein *Newname* für den Abschnitt.

Festlegen oder Ändern des Abschnitts `attributes`, geben Sie ein Komma (**,**) gefolgt von einem oder mehreren Attributzeichen. Um ein Attribut zu negieren, stehen Sie das Zeichen mit einem Ausrufezeichen (!). Die folgenden Zeichen werden arbeitsspeicherattribute angeben:

|Attribut|Einstellung|
|---------------|-------------|
|c|Code|
|T|Entfernbare|
|e|executable|
|i|Initialisiert Daten|
|k|zwischengespeicherte virtuellen Arbeitsspeicher|
|m|Link entfernen|
|o|Link-Informationen|
|p|ausgelagerter virtueller Speicher|
|b|Lesen|
|s|Freigegeben|
|n|nicht initialisierte Daten|
|m|Schreiben|

Um zu steuern *Ausrichtung*, geben Sie das Zeichen **ein** gefolgt von einem der folgenden Zeichen, die Größe der Ausrichtung in Bytes, der wie folgt festlegen:

|Zeichen|Ausrichtungsgröße in Byte|
|---------------|-----------------------------|
|1|1|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|w|keine Ausrichtung|

Geben Sie die `attributes` und *Ausrichtung* Zeichen als Zeichenfolge keine Leerzeichen. Die Zeichen sind nicht in der Groß-/Kleinschreibung beachtet.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](editbin-options.md)
