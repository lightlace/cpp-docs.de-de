---
title: errno, _doserrno, _sys_errlist und _sys_nerr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _errno
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _sys_errlist
- errno
- _sys_nerr
- _doserrno
dev_langs:
- C++
helpviewer_keywords:
- error codes, printing
- sys_errlist global variable
- doserrno global variable
- errno global variable
- _doserrno global variable
- _sys_errlist global variable
- _sys_nerr global variable
- sys_nerr global variable
ms.assetid: adbec641-6d91-4e19-8398-9a34046bd369
caps.latest.revision: 18
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
ms.openlocfilehash: dd49544eb79573216d97f6082eff5afeca12a946
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="errno-doserrno-syserrlist-and-sysnerr"></a>errno, _doserrno, _sys_errlist und _sys_nerr
Globale Makros, die während der Programmausführung festgelegte Fehlercodes und mit den Fehlercodes identische Zeichenfolgen zur Anzeige enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
#define errno   (*_errno())  
#define _doserrno   (*__doserrno())  
#define _sys_errlist (__sys_errlist())  
#define _sys_nerr (*__sys_nerr())  
```  
  
## <a name="remarks"></a>Hinweise  
 Sowohl `errno` als auch `_doserrno` werden von der Laufzeit während des Programmstarts auf 0 festgelegt. `errno` wird bei einem Fehler bei einem Aufruf auf Systemebene festgelegt. Weil `errno` den Wert für den letzten Aufruf enthält, der ihn festlegte, wird dieser Wert möglicherweise durch darauffolgende Aufrufe geändert. Laufzeit-Bibliothekaufrufe, die bei einem Fehler `errno` festlegen, löschen `errno` bei Erfolg nicht. Löschen Sie `errno` immer sofort vor einem Aufruf, der es möglicherweise festlegt, durch Aufrufen von `_set_errno(0)`, und überprüfen Sie es sofort nach dem Aufruf.  
  
 Bei einem Fehler wird `errno` nicht zwangsläufig auf den gleichen Wert festgelegt, wie der durch einen Systemaufruf zurückgegebene Fehlercode. Bei E/A-Vorgängen speichert `_doserrno` die Betriebssystem-Fehlercodeäquivalente von `errno`-Codes. Bei den meisten Nicht-E/A-Vorgängen ist der Wert von `_doserrno` nicht definiert.  
  
 Jeder `errno`-Wert wird einer Fehlermeldung in `_sys_errlist` zugeordnet, die mithilfe einer der [perror](../c-runtime-library/reference/perror-wperror.md)-Funktionen gedruckt werden kann oder mithilfe einer der [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)- oder [strerror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)-Funktionen in einer Zeichenfolge gespeichert werden kann. `perror` und `strerror` verwenden das Array `_sys_errlist` und `_sys_nerr` – die Anzahl von Elementen in `_sys_errlist` –, um Fehlerinformationen zu verarbeiten. Der direkte Zugriff auf `_sys_errlist` und `_sys_nerr` ist aus Codesicherheitsgründen veraltet. Es wird empfohlen, wie hier gezeigt anstatt der globalen Makros die sichereren, funktionsbereiten Versionen zu verwenden:  
  
|Globales Makro|Funktionsbereite Äquivalente|  
|------------------|----------------------------|  
|`_doserrno`|[_get_doserrno](../c-runtime-library/reference/get-doserrno.md), [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)|  
|`errno`|[_get_errno](../c-runtime-library/reference/get-errno.md), [_set_errno](../c-runtime-library/reference/set-errno.md)|  
|`_sys_errlist`, `_sys_nerr`|[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|  
  
 Bibliotheksmathematikroutinen legen `errno` fest, indem sie [_matherr](../c-runtime-library/reference/matherr.md) aufrufen. Um Mathematikfehler anders zu handhaben, schreiben Sie Ihre eigene Routine gemäß der `_matherr`-Verweisbeschreibung und nennen sie `_matherr`.  
  
 Alle `errno`-Werte in der folgenden Tabelle sind vordefinierte Konstanten in \<errno.h> und kompatibel mit UNIX. Nur `ERANGE`, `EILSEQ` und `EDOM` werden im Standard ISO C99 festgelegt.  
  
|Konstante|Systemfehlermeldung|Wert|  
|--------------|--------------------------|-----------|  
|`EPERM`|Dieser Vorgang ist unzulässig|1|  
|`ENOENT`|Keine solche Datei oder Verzeichnis|2|  
|`ESRCH`|Kein solcher Prozess|3|  
|`EINTR`|Unterbrochene Funktion|4|  
|`EIO`|E/A-Fehler|5|  
|`ENXIO`|Kein solches Gerät oder Adresse|6|  
|`E2BIG`|Argumentliste zu lang|7|  
|`ENOEXEC`|Exec-Formatfehler|8|  
|`EBADF`|Ungültige Dateinummer|9|  
|`ECHILD`|Keine erzeugten Prozesse|10|  
|`EAGAIN`|Keine weiteren Prozesse oder nicht genug Speicher oder maximale Schachtelungsebene erreicht|11|  
|`ENOMEM`|Nicht genügend Speicher|12|  
|`EACCES`|Berechtigung verweigert|13|  
|`EFAULT`|Ungültige Adresse|14|  
|`EBUSY`|Gerät oder Ressource beschäftigt|16|  
|`EEXIST`|Datei ist vorhanden|17|  
|`EXDEV`|Geräteübergreifende Verbindung|18|  
|`ENODEV`|Kein solches Gerät|19|  
|`ENOTDIR`|Kein Verzeichnis|20|  
|`EISDIR`|Ist ein Verzeichnis|21|  
|`EINVAL`|Ungültiges Argument|22|  
|`ENFILE`|Zu viele Dateien im System offen|23|  
|`EMFILE`|Zu viele geöffnete Dateien|24|  
|`ENOTTY`|Unzulässiger E/A-Steuerelementvorgang|25|  
|`EFBIG`|Datei zu groß|27|  
|`ENOSPC`|Kein Speicherplatz auf Gerät übrig|28|  
|`ESPIPE`|Ungültige Suche|29|  
|`EROFS`|Schreibgeschütztes Dateisystem|30|  
|`EMLINK`|Zu viele Links|31|  
|`EPIPE`|Unterbrochener senkrechter Strich|32|  
|`EDOM`|Mathematikargument|33|  
|`ERANGE`|Ergebnis zu groß|34|  
|`EDEADLK`|Deadlock von Ressourcen würde auftreten|36|  
|`EDEADLOCK`|Gleich wie EDEADLK hinsichtlich Kompatibilität mit älteren Versionen von Microsoft C|36|  
|`ENAMETOOLONG`|Dateiname zu lang|38|  
|`ENOLCK`|Keine Sperren verfügbar|39|  
|`ENOSYS`|Funktion wird nicht unterstützt|40|  
|`ENOTEMPTY`|Verzeichnis nicht leer|41|  
|`EILSEQ`|Ungültige Bytesequenz|42|  
|`STRUNCATE`|Zeichenfolge wurde abgeschnitten|80|  
  
## <a name="requirements"></a>Anforderungen  
  
|Globales Makro|Erforderlicher Header|Optionaler Header|  
|------------------|---------------------|---------------------|  
|`errno`|\<errno.h> oder \<stdlib.h>, \<cerrno> oder \<cstdlib> (C++)||  
|`_doserrno`, `_sys_errlist`, `_sys_nerr`|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h >, \<cerrno > (C++)|  
  
 Die Makros `_doserrno`, `_sys_errlist` und `_sys_nerr` sind Microsoft-Erweiterungen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)   
 [errno-Konstanten](../c-runtime-library/errno-constants.md)   
 [perror, _wperror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror, _strerror, _wcserror, \__wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)
