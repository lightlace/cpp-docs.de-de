---
title: /CLRSUPPORTLASTERROR (Letzten Fehlercode für PInvoke-Aufrufe beibehalten)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 64948d81759d415245e741bc6152d56bb35480d2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988354"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Letzten Fehlercode für PInvoke-Aufrufe beibehalten)

**/CLRSUPPORTLASTERROR**, das standardmäßig aktiviert ist, behält den letzten Fehlercode von Funktionen bei, die durch den P/Aufruf-Mechanismus aufgerufen werden. Dadurch können Sie Native Funktionen in DLLs aufrufen, von mit **/CLR**kompilierten Code.

## <a name="syntax"></a>Syntax

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Hinweise

Die Beibehaltung des letzten Fehlercodes impliziert eine Abnahme der Leistung.  Wenn Sie keine Auswirkungen auf die Leistung bei der Beibehaltung des letzten Fehlercodes haben möchten, verknüpfen Sie mit **/CLRSUPPORTLASTERROR: No**.

Sie können die Auswirkungen auf die Leistung minimieren, indem Sie eine Verknüpfung mit **/CLRSUPPORTLASTERROR: SYSTEMDLL**herstellen, die nur den letzten Fehlercode für Funktionen in System-DLLs beibehält.  Eine System-dll ist als eine der folgenden Einstellungen definiert:

|||||
|-|-|-|-|
|Aclui. DLL|ACTIVEDS. DLL|Adptif. DLL|Advapi32. DLL|
|Asycflt. DLL|Authz. DLL|AVICAP32.DLL|AVIFIL32.DLL|
|KEs. DLL|CLUSAPI. DLL|COMCTL32.DLL|Comdlg32. DLL|
|Comsvcs. DLL|Mit der Eingabe. DLL|CRYPT32. DLL|Cryptnet. DLL|
|CRYPTUI. DLL|D3D8THK. DLL|Dbgeng. DLL|DBGHELP. DLL|
|DCIMAN32.DLL|Dnsapi. DLL|Dsprop. DLL|Dsuiext. DLL|
|GDI32.DLL|GLU32.DLL|Hlink. DLL|ICM32.DLL|
|"Imagehlp. DLL|IMM32.DLL|Iphlpapi. DLL|Iprop. DLL|
|KERNEL32.DLL|Ksuser. DLL|LOADPERF. DLL|LZ32.DLL|
|Datei "Mapi32. DLL|Mgmtapi. DLL|"Mubsync". DLL|MPR. DLL|
|MPRAPI. DLL|MQRT.DLL|MSACM32.DLL|MSCMS.DLL|
|MSI. DLL|MSIMG32. DLL|Msrating. DLL|Mstask. DLL|
|MSVFW32.DLL|Mswap. DLL|Mtxex. DLL|Nddecoapi. DLL|
|NETAPI32. DLL|Npptools. DLL|NTDSAPI. DLL|NTDSBCLI.DLL|
|NtmsApi. DLL|ODBC32.DLL|ODBCBCP.DLL|OLE32.DLL|
|Oleacc. DLL|Oleaut32. DLL|Oledlg. DLL|OPENGL32. DLL|
|PDH. DLL|POWRPROF. DLL|Qosname. DLL|Such. DLL|
|RASAPI32.DLL|Rasdlg. DLL|Rassapi. DLL|Resutils. DLL|
|Riched20. DLL|RPCNS4.DLL|RPCRT4.DLL|RTM. DLL|
|Rtutils. DLL|Scarddlg. DLL|SECUR32. DLL|Sensorapi. DLL|
|Setupapi. DLL|SFC. DLL|Shell32. DLL|SHFOLDER. DLL|
|Shlwapi. DLL|Sisbkup. DLL|Snmpapi. DLL|Srclient. DLL|
|D. DLL|TAPI32. DLL|Verkehrssicher. DLL|Urne. DLL|
|URLMON.DLL|User32. DLL|USERENV. DLL|USP10.DLL|
|UXTHEME. DLL|VDMDBG. DLL|Version. DLL|WinFax. DLL|
|WINHTTP.DLL|WinInet. DLL|WINMM. DLL|WINSCARD. DLL|
|WINTRUST. DLL|WLDAP32.DLL|WOW32.DLL|WS2_32.DLL|
|WSNMP32.DLL|WSOCK32.DLL|WTSAPI32.DLL|Xolehlp. DLL|

> [!NOTE]
>  Die Beibehaltung des letzten Fehlers wird nicht für nicht verwaltete Funktionen unterstützt, die von CLR-Code im selben Modul genutzt werden.

- Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **Linker**.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option im Feld **zusätzliche Optionen** ein.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine native dll mit einer exportierten Funktion definiert, die den letzten Fehler ändert.

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die dll verwendet, und es wird gezeigt, wie **/CLRSUPPORTLASTERROR**verwendet wird.

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
