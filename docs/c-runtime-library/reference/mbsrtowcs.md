---
title: mbsrtowcs
ms.date: 11/04/2016
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
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 2bc0c8c9e2d871b6d1748c42dc02c627244dbf69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597144"
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
Die maximale Anzahl von Zeichen (nicht Bytes), konvertieren und speichern *Wcstr*.

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** konvertierungszustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, wird ein statisches internes Konvertierungszustandsobjekt verwendet. Da das interne **Mbstate_t** Objekt nicht threadsicher, es wird empfohlen, dass Sie immer Ihren eigenen übergeben *Mbstate* Parameter.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Zeichen zurück, die erfolgreich konvertiert wurden, nicht einschließlich des abschließenden Zeichens NULL, sofern vorhanden. Gibt ((size_t)(-1) bei ein Fehler ist aufgetreten, und legt **Errno** auf eilseq fest.

## <a name="remarks"></a>Hinweise

Die **Mbsrtowcs** -Funktion konvertiert eine Zeichenfolge mit Multibytezeichen, die indirekt verweist *Mbstr*, in Breitzeichen, die in den Puffer, die auf gespeicherten *Wcstr*, Mithilfe des in enthaltenen Konvertierungsstatus *Mbstate*. Die Konvertierung wird fortgesetzt, für jedes Zeichen bis entweder ein abschließendes Multibytezeichen null gefunden wird, eine multibyte-Sequenz, die keine gültigen Zeichen im aktuellen Gebietsschema entspricht festgestellt wird, oder bis *Anzahl* Zeichen wurden konvertiert. Wenn **Mbsrtowcs** die multibyte-Nullzeichen ('\0') erkennt, entweder vor oder bei *Anzahl* auftritt, konvertiert es in ein abschließendes Nullzeichen von 16-Bit- und beendet wird.

Daher die Breitzeichen-Zeichenfolge an *Wcstr* ist Null-terminierte nur, wenn **Mbsrtowcs** während der Konvertierung ein Multibytezeichen Null findet. Wenn die Sequenzen, zeigt *Mbstr* und *Wcstr* überlappen, ist das Verhalten der **Mbsrtowcs** ist nicht definiert. **Mbsrtowcs** wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.

Die **Mbsrtowcs** Funktion unterscheidet sich von [Mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) durch die neustartmöglichkeit. Der konvertierungszustand befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Z. B. eine Anwendung verwendet soll **Mbsrlen** anstelle von **Mbslen**, wenn ein nachfolgender Aufruf von **Mbsrtowcs** anstelle **Mbstowcs**.

Wenn *Wcstr* ist kein null-Zeiger, das Zeigerobjekt verweist *Mbstr* wird einen null-Zeiger zugewiesen, wenn die Konvertierung beendet, da ein abschließendes Nullzeichen erreicht wurde. Andernfalls wird es ggf. der Adresse unmittelbar nach dem letzten konvertierten Multibytezeichen zugewiesen. Auf diese Weise kann ein nachfolgender Funktionsaufruf die Konvertierung an der Stelle neu starten, an der der Aufruf beendet wurde.

Wenn die *Wcstr* Argument ist ein null-Zeiger der *Anzahl* Argument wird ignoriert, und **Mbsrtowcs** gibt die erforderliche Größe in Breitzeichen, für die Zielzeichenfolge zurück. Wenn *Mbstate* ist ein null-Zeiger, der die Funktion verwendet eine nicht threadsichere statische interne **Mbstate_t** konvertierungszustandsobjekt. Wenn die Zeichensequenz *Mbstr* verfügt nicht über eine entsprechende Multibyte zeichendarstellung verfügt, wird-1 zurückgegeben und die **Errno** nastaven NA hodnotu **EILSEQ**.

Wenn *Mbstr* ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt-1 zurück.

In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Mbsrtowcs** -Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread ruft **Setlocale** solange diese Funktion ausgeführt wird und die *Mbstate* Argument ist kein null-Zeiger.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
