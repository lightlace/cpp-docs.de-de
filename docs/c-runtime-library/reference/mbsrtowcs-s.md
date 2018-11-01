---
title: mbsrtowcs_s
ms.date: 11/04/2016
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: a935b5181078f3b08ba5f2f89c581ed8cce8ded5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588825"
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s

Konvertieren einer Zeichenfolge mit Multibytezeichen im aktuellen Gebietsschema in die entsprechende Zeichenfolge mit Breitzeichen. Eine Version von [mbsrtowcs](mbsrtowcs.md) mit Sicherheitserweiterungen wie sie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben ist.

## <a name="syntax"></a>Syntax

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Die Anzahl von konvertierten Zeichen.

*wcstr*<br/>
Pufferadresse zum Speichern der resultierenden konvertierten Zeichenfolge mit Breitzeichen.

*sizeInWords*<br/>
Die Größe des *Wcstr* in Wörtern (Breitzeichen).

*mbstr*<br/>
Indirekter Zeiger auf den Speicherort der Multibyte-Zeichenfolge, die konvertiert werden soll.

*count*<br/>
Die maximale Anzahl von Breitzeichen, das Speichern in der *Wcstr* Puffer, ohne das abschließende Nullzeichen oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** konvertierungszustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, wird ein statisches internes Konvertierungszustandsobjekt verwendet. Da das interne **Mbstate_t** Objekt nicht threadsicher, es wird empfohlen, dass Sie immer Ihren eigenen übergeben *Mbstate* Parameter.

## <a name="return-value"></a>Rückgabewert

Null, wenn die Konvertierung erfolgreich ist, oder ein Fehlercode bei einem Fehler.

|Fehlerbedingung|Rückgabewert und **Errno**|
|---------------------|------------------------------|
|*Wcstr* ist ein null-Zeiger und *SizeInWords* > 0|**EINVAL**|
|*Mbstr* ist ein null-Zeiger|**EINVAL**|
|Die Zeichenfolge indirekt verweist *Mbstr* enthält eine multibyte-Sequenz, die für das aktuelle Gebietsschema ungültig ist.|**EILSEQ**|
|Der Zielpuffer ist zu klein, um die konvertierte Zeichenfolge enthalten (es sei denn, *Anzahl* ist **_TRUNCATE**; Weitere Informationen finden Sie unter "Hinweise")|**ERANGE**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion einen Fehlercode zurück und legt **Errno** wie in der Tabelle angegeben.

## <a name="remarks"></a>Hinweise

Die **Mbsrtowcs_s** -Funktion konvertiert eine Zeichenfolge mit Multibytezeichen, die indirekt verweist *Mbstr* in Breitzeichen, die in den Puffer, die auf gespeicherten *Wcstr*, Mithilfe des in enthaltenen Konvertierungsstatus *Mbstate*. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:

- Ein Multibyte-Nullzeichen wird erkannt.

- Ein ungültiges Multibytezeichen wird erkannt.

- Die Anzahl der gespeicherten Breitzeichen die *Wcstr* Puffer ist gleich *Anzahl*.

Die Zielzeichenfolge *Wcstr* ist immer Null-terminiert ist, selbst bei einem Fehler, es sei denn, *Wcstr* ist ein null-Zeiger.

Wenn *Anzahl* der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md), **Mbsrtowcs_s** konvertiert Anteil der Zeichenfolge wie in den Zielpuffer passt, und weiterhin Platz für ein NULL-Wert Abschlusszeichen.

Wenn **Mbsrtowcs_s** die Quellzeichenfolge erfolgreich konvertiert wird die Größe in Breitzeichen der konvertierten Zeichenfolge und der null-Terminator in  *&#42;pReturnValue*aus  *pReturnValue* ist kein null-Zeiger. Dies tritt auf, auch wenn die *Wcstr* Argument ist ein null-Zeiger und die erforderliche Puffergröße bestimmen. Beachten Sie, dass bei *Wcstr* ist ein null-Zeiger *Anzahl* wird ignoriert.

Wenn *Wcstr* ist kein null-Zeiger, das Zeigerobjekt verweist *Mbstr* wird einen null-Zeiger zugewiesen, wenn die Konvertierung beendet, da ein abschließendes Nullzeichen erreicht wurde. Andernfalls wird es ggf. der Adresse unmittelbar nach dem letzten konvertierten Multibytezeichen zugewiesen. Auf diese Weise kann ein nachfolgender Funktionsaufruf die Konvertierung an der Stelle neu starten, an der der Aufruf beendet wurde.

Wenn *Mbstate* ist ein null-Zeiger der internen Bibliothek **Mbstate_t** statische konvertierungszustandsobjekt verwendet wird. Da dieses interne statische Objekt nicht threadsicher ist, es wird empfohlen, dass Sie Ihre eigenen übergeben *Mbstate* Wert.

Wenn **Mbsrtowcs_s** findet ein Multibytezeichen, die im aktuellen Gebietsschema ungültig ist-1 und speichert Sie im  *&#42;pReturnValue*, der Zielpuffer *Wcstr* Klicken Sie auf eine leere Zeichenfolge festgelegt **Errno** zu **EILSEQ**, und gibt **EILSEQ**.

Wenn die Sequenzen, zeigt *Mbstr* und *Wcstr* überlappen, ist das Verhalten der **Mbsrtowcs_s** ist nicht definiert. **Mbsrtowcs_s** wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.

> [!IMPORTANT]
> Sicherstellen, dass *Wcstr* und *Mbstr* nicht überlappen und dass *Anzahl* die Anzahl zu konvertierendermultibytezeichen korrekt darstellt.

Die **Mbsrtowcs_s** Funktion unterscheidet sich von [_mbsnbcpy_s, _mbsnbcpy_s_l](mbstowcs-s-mbstowcs-s-l.md) durch die neustartmöglichkeit. Der konvertierungszustand befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Z. B. eine Anwendung verwendet soll **Mbsrlen** anstelle von **Mbslen**, wenn ein nachfolgender Aufruf von **Mbsrtowcs_s** anstelle **Mbstowcs_s**.

In C++ wird die Verwendung dieser Funktion durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Mbsrtowcs_s** -Funktion ist multithreadsicher ist, wenn keine Funktion in der aktuellen Thread ruft **Setlocale** solange diese Funktion ausgeführt wird und die *Mbstate* Argument ist keine null-Zeiger.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
