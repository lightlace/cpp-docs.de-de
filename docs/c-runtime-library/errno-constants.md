---
title: "errno-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ENOEXEC"
  - "ENOMEM"
  - "E2BIG"
  - "STRUNCATE"
  - "ENOENT"
  - "EMFILE"
  - "EBADF"
  - "EDEADLOCK"
  - "EXDEV"
  - "EILSEQ"
  - "EINVAL"
  - "EDOM"
  - "EACCES"
  - "ERANGE"
  - "ENOSPC"
  - "EAGAIN"
  - "EEXIST"
  - "ECHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E2BIG-Konstante"
  - "EACCES-Konstante"
  - "EAGAIN-Konstante"
  - "EBADF-Konstante"
  - "ECHILD-Konstante"
  - "EDEADLOCK-Konstante"
  - "EDOM-Konstante"
  - "EEXIST-Konstante"
  - "EILSEQ-Konstante"
  - "EINVAL-Konstante"
  - "EMFILE-Konstante"
  - "ENOENT-Konstante"
  - "ENOEXEC-Konstante"
  - "ENOMEM-Konstante"
  - "ENOSPC-Konstante"
  - "ERANGE-Konstante"
  - "errno-Konstanten"
  - "EXDEV-Konstante"
  - "STRUNCATE-Konstante"
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# errno-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <errno.h>  
```  
  
## Hinweise  
 Die **errno**\-Werte sind die Konstanten, die im Fall der [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) verschiedene Fehlerbedingungen zugewiesen werden.  
  
 ERRNO.H enthält die Definitionen der **errno**\-Werte.  Jedoch werden nicht alle Definitionen, die in ERRNO.H angegeben werden, in 32\-Bit\-Windows\-Betriebssystemen verwendet.  Einige der Werte in ERRNO.H sind vorhanden, Kompatibilität mit der UNIX\-Familie von Betriebssystemen beizubehalten.  
  
 Die **errno**\-Werte in ein 32\-Bit\-Windows\-Betriebssystem sind eine Teilmenge der Werte für **errno** in XENIX\-Systemen.  Daher ist der **errno**\-Wert nicht unbedingt dem eigentlichen Fehlercode, der durch einen Systemaufruf von Windows\-Betriebssystemen zurückgegeben wird.  Um auf den tatsächlichen Betriebssystemfehlercode zuzugreifen, verwenden Sie die [\_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)\-Variable, die diesen Wert enthält.  
  
 Die folgenden Werte werden unterstützt: **errno**  
  
 **ECHILD**  
 Keine erstellten Prozesse.  
  
 **EAGAIN**  
 Nicht mehr Prozesse.  Ein Versuch, einen neuen Prozess zu erstellen Fehler aus, da sie nicht mehr Prozessslots gibt, oder es ist nicht genügend Arbeitsspeicher, oder die maximale Schachtelungsebene ist erreicht wurde.  
  
 **E2BIG**  
 Argumentliste zu lang.  
  
 **EACCES**  
 Zugriff verweigert.  Die Berechtigungseinstellung der Datei kann nicht den angegebenen Zugriff.  Dieser Fehler gibt an, dass versucht, eine Datei \(oder in einigen Fällen auf ein Verzeichnis\) so Zugriff ausgeführt wurde, die mit den Dateiattributen nicht kompatibel ist.  
  
 Beispielsweise kann der Fehler auftreten, wenn ein Versuch, in einer Datei zu lesen, die nicht angezeigt wird, um eine vorhandene schreibgeschützte Datei zum Schreiben zu öffnen, oder ein Verzeichnis anstelle einer Datei zu öffnen gemacht wird.  Unter MS\-DOS Betriebssystemversionen 3.0 und höher, gibt **EACCES** auch einer Sperre oder eine Zugriffsverletzung an.  
  
 Der Fehler kann auch auftreten, um eine Datei oder ein Verzeichnis umbenannt oder ein vorhandenes Verzeichnis zu entfernen.  
  
 **EBADF**  
 Ungültiges Dateinummern.  Es gibt zwei mögliche Ursachen: 1\) ist der angegebene Dateideskriptor kein gültiger Wert oder bezieht sich nicht auf eine geöffnete Datei. 2\) Es wurde versucht, in einer Datei oder einem Gerät schreiben gemacht, die für den schreibgeschützten Zugriff geöffnet waren.  
  
 **EDEADLOCK**  
 Ressourcendeadlock würde auftreten.  Das Argument einer mathematischen Funktion ist in der Domäne der Funktion.  
  
 **EDOM**  
 Mathematisches Argument.  
  
 **EEXIST**  
 Dateien vorhanden sind.  Es wurde versucht, eine Datei erstellt wurde, die bereits vorhanden ist.  Beispielsweise werden **\_O\_CREAT** und **\_O\_EXCL** die Flags in einem **\_open** Aufruf angegeben, die benannte Datei ist bereits vorhanden.  
  
 **EILSEQ**  
 Ungültige Bytesequenz, \(beispielsweise in einer MBCS\-Zeichenfolge\).  
  
 **EINVAL**  
 Ungültiges Argument.  Ein ungültiger Wert wurde für eines der Argumente an eine Funktion übergeben.  Beispielsweise der Wert zugewiesen für den Ursprung, wenn, einen Dateizeiger zu positionieren \(mithilfe eines Aufrufs von **fseek**\) voranstellen dem Anfang der Datei.  
  
 **EMFILE**  
 So viele Dateien geöffnet.  Nicht mehr Dateideskriptoren sind verfügbar, sodass nicht mehr Dateien geöffnet werden.  
  
 **ENOENT**  
 keine derartige Datei oder Verzeichnis.  Die angegebene Datei oder das Verzeichnis ist nicht vorhanden oder kann nicht gefunden werden.  Diese Meldung kann auftreten, wenn eine angegebene Datei nicht vorhanden ist, oder eine Komponente eines Pfades keinen vorhandenen Verzeichnis angibt.  
  
 **ENOEXEC**  
 Leitprogrammformatfehler.  Es wurde versucht, eine Datei auszuführen gemacht, die nicht ausgeführt werden kann, oder die ein ungültiges Format einer ausführbaren Datei wird.  
  
 **ENOMEM**  
 Nicht genug wurden.  Nicht genügend Arbeitsspeicher ist für der angeforderten Operator verfügbar.  Beispielsweise kann diese Meldung auftreten, wenn unzulänglicher Arbeitsspeicher verfügbar ist, einen untergeordneten Prozess auszuführen oder die Zuordnungsanforderung in einem **\_getcwd** Aufruf nicht erfüllt werden kann.  
  
 **ENOSPC**  
 Kein Speicherplatz links auf Gerät.  Nicht mehr Platz zum Schreiben ist auf dem Gerät verfügbar \(beispielsweise, wenn der Datenträger voll ist\).  
  
 **ERANGE**  
 Ergebnis zu groß.  Ein Argument einer mathematischen Funktion ist, mit dem Ergebnis des partiellen oder gesamten Verlust des Schritts im Ergebnis zu groß.  Dieser Fehler kann in anderen Funktionen auch auftreten, wenn ein Argument größer als erwartet ist \(beispielsweise, wenn das *Pufferargument* zu **\_getcwd** länger als erwartet ist\).  
  
 **EXDEV**  
 Verweis über für das Dateisystem zulässigen Wert.  Es wurde versucht, eine Datei auf einem anderen Gerät zu verschieben gemacht \(mithilfe der **umbenennen**\-Funktion\).  
  
 **STRUNCATE**  
 Eine Zeichenfolgenkopie oder \-Verkettung führten abgeschnittene eine Zeichenfolge.  Siehe [\_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Die folgenden Werte werden für die Kompatibilität mit Posix unterstützt.  Sie können Werte auf erforderliche nicht\-\-Posix Systemen.  
  
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
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)