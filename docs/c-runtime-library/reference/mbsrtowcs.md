---
title: mbsrtowcs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff120fea2ec3f1ea659233ccee3f66514d0fd76b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="mbsrtowcs"></a>mbsrtowcs
Konvertiert eine Zeichenfolge mit Multibytezeichen im aktuellen Gebietsschema in die entsprechende Zeichenfolge mit Breitzeichen, mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 [out] `wcstr`  
 Adresse zum Speichern der resultierenden konvertierten Zeichenfolge mit Breitzeichen.  
  
 [in, out] `mbstr`  
 Indirekter Zeiger auf den Speicherort der zu konvertierenden Zeichenfolge mit Multibytezeichen.  
  
 [in] `count`  
 Die maximale Anzahl von Zeichen (nicht Bytes), die konvertiert und in `wcstr` gespeichert werden sollen.  
  
 [in, out] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`-Konvertierungszustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, wird ein statisches internes Konvertierungszustandsobjekt verwendet. Da das interne `mbstate_t`-Objekt nicht threadsicher ist, wird empfohlen, immer Ihren eigenen `mbstate`-Parameter zu übergeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Zeichen zurück, die erfolgreich konvertiert wurden, nicht einschließlich des abschließenden Zeichens NULL, sofern vorhanden. Gibt (size_t)(-1) bei einem Fehler zurück und legt `errno` auf EILSEQ fest.  
  
## <a name="remarks"></a>Hinweise  
 Die `mbsrtowcs`-Funktion konvertiert eine Zeichenfolge mit Multibytezeichen, auf die indirekt von `mbstr` verwiesen wird, in im Puffer gespeicherte Breitzeichen, auf die von `wcstr` verwiesen wird, und verwendet dafür den in `mbstate` enthaltenen Konvertierungszustand. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis entweder ein abschließendes Multibytezeichen NULL oder eine Multibytesequenz gefunden wird, die keinem gültigen Zeichen im aktuellen Gebietsschema entspricht, oder bis `count` Zeichen konvertiert wurden. Wenn `mbsrtowcs` das Multibytezeichen NULL ('\0') erkennt, entweder vor oder bei `count`, wird es in ein abschließendes 16-Bit-Zeichen NULL konvertiert und beendet.  
  
 Folglich endet die Breitzeichen-Zeichenfolge bei `wcstr` nur dann auf NULL, wenn `mbsrtowcs` während der Konvertierung ein Multibytezeichen NULL findet. Wenn die Sequenzen, auf die von `mbstr` und `wcstr` verwiesen wird, überlappen, ist das Verhalten von `mbsrtowcs` nicht definiert. `mbsrtowcs` wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
 Die `mbsrtowcs`-Funktion unterscheidet sich von [mbstowcs_s](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Beispiel: Eine Anwendung soll `mbsrlen` anstelle von `mbslen` verwenden, wenn ein nachfolgender Aufruf von `mbsrtowcs` anstelle von `mbstowcs.` verwendet wird.  
  
 Wenn `wcstr` kein NULL-Zeiger ist, wird das Zeigerobjekt, auf das von `mbstr` verwiesen wird, einem NULL-Zeiger zugewiesen, wenn die Konvertierung beendet wird, da ein abschließendes Nullzeichen erreicht wurde. Andernfalls wird es ggf. der Adresse unmittelbar nach dem letzten konvertierten Multibytezeichen zugewiesen. Auf diese Weise kann ein nachfolgender Funktionsaufruf die Konvertierung an der Stelle neu starten, an der der Aufruf beendet wurde.  
  
 Wenn das `wcstr`-Argument ein NULL-Zeiger ist, wird das `count`-Argument ignoriert, und `mbsrtowcs` gibt die erforderliche Größe in Breitzeichen für die Zielzeichenfolge zurück. Wenn `mbstate` ein NULL-Zeiger ist, verwendet die Funktion ein nicht threadsicheres statisches internes `mbstate_t`-Konvertierungszustandsobjekt. Wenn die Zeichensequenz `mbstr` nicht über eine entsprechende Multibyte-Zeichendarstellung verfügt, wird -1 zurückgegeben, und `errno` wird auf `EILSEQ` festgelegt.  
  
 Wenn `mbstr` ein NULL-Zeiger ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "-1" zurück.  
  
 In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `mbsrtowcs`-Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread `setlocale` aufruft, solange diese Funktion ausgeführt wird und das `mbstate`-Argument kein NULL-Zeiger ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`mbsrtowcs`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)