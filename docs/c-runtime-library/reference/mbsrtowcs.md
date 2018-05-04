---
title: mbsrtowcs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbsrtowcs
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb5bda16238888905678ffb3b6de01b93555ad0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Konvertiert eine Zeichenfolge mit Multibytezeichen im aktuellen Gebietsschema in die entsprechende Zeichenfolge mit Breitzeichen, mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [mbsrtowcs_s](mbsrtowcs-s.md).

## <a name="syntax"></a>Syntax

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*wcstr*<br/>
Adresse zum Speichern der resultierenden konvertierten Zeichenfolge mit Breitzeichen.

*mbstr*<br/>
Indirekter Zeiger auf den Speicherort der zu konvertierenden Zeichenfolge mit Multibytezeichen.

*count*<br/>
Die maximale Anzahl von Zeichen (nicht Bytes) zu konvertieren und in speichern *Wcstr*.

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** konvertierungszustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, wird ein statisches internes Konvertierungszustandsobjekt verwendet. Da das interne **Mbstate_t** -Objekt nicht threadsicher, es wird empfohlen, dass Sie immer eigene übergeben *Mbstate* Parameter.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Zeichen zurück, die erfolgreich konvertiert wurden, nicht einschließlich des abschließenden Zeichens NULL, sofern vorhanden. Gibt ((size_t)(-1) bei ein Fehler aufgetreten ist, und legt **Errno** auf eilseq fest.

## <a name="remarks"></a>Hinweise

Die **Mbsrtowcs** -Funktion konvertiert eine Zeichenfolge mit Multibytezeichen indirekt verweist *Mbstr*, im verweist Puffer gespeicherte Breitzeichen *Wcstr*, über mithilfe den in enthaltenen konvertierungszustand *Mbstate*. Die Konvertierung wird fortgesetzt, für jedes Zeichen bis entweder ein abschließendes null multibyte-Zeichen gefunden wird, eine multibyte-Sequenz, die nicht in ein gültiges Zeichen im aktuellen Gebietsschema entsprechen festgestellt wird, oder bis *Anzahl* Zeichen wurden konvertiert. Wenn **Mbsrtowcs** das Multibytezeichen Null-Zeichen ('\0') erkennt, entweder vor oder bei *Anzahl* auftritt, konvertiert es in ein abschließendes Nullzeichen von 16-Bit- und nicht länger auf.

Daher die Breitzeichen-Zeichenfolge bei *Wcstr* ist Null-terminierte nur, wenn **Mbsrtowcs** ein Multibytezeichen Null findet, bei der Konvertierung. Wenn die Sequenzen auf verweist *Mbstr* und *Wcstr* überlappen, ist das Verhalten des **Mbsrtowcs** ist nicht definiert. **Mbsrtowcs** wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.

Die **Mbsrtowcs** -Funktion unterscheidet sich von [Mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) durch die neustartmöglichkeit. Der konvertierungszustand wird gespeichert, *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbarer Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte verwenden, z. B. **Mbsrlen** anstelle von **Mbslen**, wenn ein nachfolgender Aufruf von **Mbsrtowcs** anstelle von **Mbstowcs**.

Wenn *Wcstr* ist kein Nullzeiger ist, das Zeigerobjekt verweist *Mbstr* ist einen null-Zeiger zugewiesen, wenn die Konvertierung beendet, da ein abschließendes Nullzeichen erreicht wurde. Andernfalls wird es ggf. der Adresse unmittelbar nach dem letzten konvertierten Multibytezeichen zugewiesen. Auf diese Weise kann ein nachfolgender Funktionsaufruf die Konvertierung an der Stelle neu starten, an der der Aufruf beendet wurde.

Wenn die *Wcstr* Argument ist ein null-Zeiger der *Anzahl* Argument wird ignoriert und **Mbsrtowcs** gibt die erforderliche Größe in Breitzeichen für die Zielzeichenfolge zurück. Wenn *Mbstate* ist ein null-Zeiger verwendet die Funktion ein nicht threadsicheres statisches internes **Mbstate_t** konvertierungszustandsobjekt. Wenn die Zeichensequenz *Mbstr* verfügt nicht über eine entsprechende Multibyte zeichendarstellung, wird-1 zurückgegeben und die **Errno** festgelegt ist, um **EILSEQ**.

Wenn *Mbstr* null-Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt-1 zurück.

In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Mbsrtowcs** -Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread ruft **Setlocale** solange diese Funktion ausgeführt wird und die *Mbstate* Argument ist ein null-Zeiger.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
