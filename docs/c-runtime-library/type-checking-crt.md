---
title: Typüberprüfung (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: bb5aecc2b47aa8e88666f42d8022395bf99fd85e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747682"
---
# <a name="type-checking-crt"></a>Typüberprüfung (CRT)

Der Compiler führt eine beschränkte Typüberprüfung für Funktionen durch, die eine variable Anzahl von Argumenten aufnehmen können, wie im Folgenden beschrieben wird:

|Funktionsaufruf |Typgeprüfte Argumente|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Erstes Argument (Formatzeichenfolge)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Die ersten zwei Argumente (Datei oder Puffer und Formatzeichenfolge)|
|`_snprintf_s`|Die ersten drei Argumente (Datei oder Puffer, Anzahl und Formatzeichenfolge)|
|`_open`|Die ersten zwei Argumente (Pfad und `_open`-Flag)|
|`_sopen_s`|Die ersten drei Argumente (Pfad, `_open`-Flag und Freigabemodus)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Die ersten zwei Argumente (Pfad und erster Argumentzeiger)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Die ersten drei Argumente (Moduskennzeichnung, Pfad und erster Argumentzeiger)|

Der Compiler führt dieselbe beschränkte Typüberprüfung für die äquivalenten Breitzeichen dieser Funktionen durch.

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
