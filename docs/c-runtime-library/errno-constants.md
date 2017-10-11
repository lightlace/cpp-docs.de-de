---
title: errno-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ENOEXEC
- ENOMEM
- E2BIG
- STRUNCATE
- ENOENT
- EMFILE
- EBADF
- EDEADLOCK
- EXDEV
- EILSEQ
- EINVAL
- EDOM
- EACCES
- ERANGE
- ENOSPC
- EAGAIN
- EEXIST
- ECHILD
dev_langs:
- C++
helpviewer_keywords:
- ENOEXEC constant
- EBADF constant
- EAGAIN constant
- EINVAL constant
- ENOENT constant
- errno constants
- E2BIG constant
- EMFILE constant
- EDEADLOCK constant
- ENOSPC constant
- EDOM constant
- ENOMEM constant
- EACCES constant
- EEXIST constant
- STRUNCATE constant
- ERANGE constant
- ECHILD constant
- EXDEV constant
- EILSEQ constant
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: fdfb4477b4de30221a0e89db02cd45178b70db0a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="errno-constants"></a>errno-Konstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <errno.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **errno**-Werte sind Konstanten, die [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bei verschiedenen Fehlerbedingungen zugewiesen werden.  
  
 ERRNO.H enthält die Definitionen der **errno**-Werte. Jedoch werden nicht alle in ERRNO.H enthaltenen Definitionen in 32-Bit-Windows-Betriebssystemen verwendet. Einige der Werte in ERRNO.H dienen dazu, die Kompatibilität mit der UNIX-Betriebssystemfamilie beizubehalten.  
  
 Die **errno**-Werte in einem 32-Bit-Windows-Betriebssystem sind eine Teilmenge der Werte für **errno** in XENIX-Systemen. Darum ist der **errno**-Wert nicht unbedingt identisch mit dem eigentlichen Fehlercode, der durch einen Systemaufruf von Windows-Betriebssystemen zurückgeben wird. Um auf den tatsächlichen Betriebssystemfehlercode zuzugreifen, verwenden Sie die [_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)-Variable, die diesen Wert enthält.  
  
 Die folgenden **errno**-Werte werden unterstützt:  
  
 **ECHILD**  
 Keine generierten Prozesse.  
  
 **EAGAIN**  
 Keine weiteren Prozesse. Fehler beim Versuch, einen neuen Prozess zu erstellen, da keine weiteren Steckplätze mehr vorhanden sind, der Arbeitsspeicher nicht ausreicht oder die maximale Schachtelungsebene erreicht wurde.  
  
 **E2BIG**  
 Argumentliste ist zu lang.  
  
 **EACCES**  
 Berechtigung verweigert. Aufgrund der Dateiberechtigungen wird der Zugriff im angegebenen Modus verweigert. Diese Fehlermeldung gibt an, dass versucht wurde, auf eine mit den Attributen der Datei inkompatible Weise auf eine Datei (oder in einigen Fällen ein Verzeichnis) zuzugreifen.  
  
 Beispielsweise kann der Fehler bei dem Versuch auftreten, aus einer nicht geöffneten Datei zu lesen, eine vorhandene schreibgeschützte Datei zum Schreiben zu öffnen oder ein Verzeichnis anstelle einer Datei zu öffnen. Ab MS-DOS-Version 3.0 kann **EACCES** möglicherweise auch auf eine Sperr- oder Freigabeverletzung hinweisen.  
  
 Der Fehler kann auch bei dem Versuch auftreten, eine Datei oder ein Verzeichnis umzubenennen oder ein vorhandenes Verzeichnis zu entfernen.  
  
 **EBADF**  
 Ungültige Dateinummer. Es gibt zwei mögliche Ursachen: 1) Der angegebene Dateideskriptor ist kein gültiger Wert oder verweist nicht auf eine geöffnete Datei. 2) Es wurde versucht, in eine Datei oder ein Gerät zu schreiben, die/das nur für schreibgeschützten Zugriff geöffnet ist.  
  
 **EDEADLOCK**  
 Deadlock von Ressourcen würde auftreten. Das an eine mathematische Funktion übergebene Argument ist nicht in der Domäne der Funktion.  
  
 **EDOM**  
 Mathematikargument.  
  
 **EEXIST**  
 Dateien sind vorhanden. Es wurde versucht, eine Datei zu erstellen, die bereits vorhanden ist. Die Flags **_O_CREAT** und **_O_EXCL** werden in einem **_open**-Aufruf angegeben, aber die angegebene Datei ist bereits vorhanden.  
  
 **EILSEQ**  
 Ungültige Folge von Bytes (z.B. in einer MBCS-Zeichenfolge).  
  
 **EINVAL**  
 Ungültiges Argument. Für eines der an eine Funktion übergebenen Argumente wurde ein ungültiger Wert angegeben. Beispiel: Der für den Ursprung einer Dateizeigerpositionierung (durch einen Aufruf von **Fseek**) angegebene Wert liegt vor dem Anfang der Datei.  
  
 **EMFILE**  
 Zu viele geöffnete Dateien. Es sind keine weiteren Dateideskriptoren verfügbar, sodass keine Dateien mehr geöffnet werden können.  
  
 **ENOENT**  
 Datei oder Verzeichnis nicht vorhanden. Die angegebene Datei oder das angegebene Verzeichnis ist nicht vorhanden oder wurde nicht gefunden. Diese Meldung kann auftreten, wenn eine angegebene Datei nicht vorhanden ist, oder eine Komponente eines Pfads kein vorhandenes Verzeichnis angibt.  
  
 **ENOEXEC**  
 Exec-Formatfehler. Es wurde versucht, eine Datei auszuführen, die nicht ausführbar ist oder ein für eine ausführbare Datei ungültiges Format besitzt.  
  
 **ENOMEM**  
 Der Kern reicht nicht aus. Es ist nicht genügend Arbeitsspeicher für den versuchten Operator verfügbar. Diese Meldung kann z.B. auftreten, wenn nicht genügend Arbeitsspeicher verfügbar ist, um einen untergeordneten Prozess auszuführen, oder wenn die Zuordnungsanforderung in einem **_getcwd**-Aufruf nicht erfüllt werden kann.  
  
 **ENOSPC**  
 Kein Speicherplatz auf dem Gerät übrig. Auf dem Gerät ist kein Speicherplatz zum Schreiben mehr verfügbar (wenn z.B. der Datenträger voll ist).  
  
 **ERANGE**  
 Ergebnis zu groß. Ein an eine mathematische Funktion übergebenes Argument ist zu groß, was zu teilweisem oder vollständigem Bedeutungsverlust im Ergebnis führt. Dieser Fehler kann auch in anderen Funktionen auftreten, wenn ein Argument größer als erwartet ist (wenn z.B. das *buffer*-Argument für **_getcwd** länger als erwartet ist).  
  
 **EXDEV**  
 Geräteübergreifende Verbindung. Es wurde versucht, eine Datei (mithilfe der **rename**-Funktion) zu einem anderen Gerät zu verschieben.  
  
 **STRUNCATE**  
 Eine Zeichenfolgenkopie oder Verkettung resultierte in einer abgeschnittenen Zeichenfolge. Siehe [_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Die folgenden Werte werden für die Kompatibilität mit Posix unterstützt. Auf Nicht-Posix-Systemen sind sie erforderliche Werte.  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)
