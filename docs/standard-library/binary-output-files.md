---
title: Binäre Ausgabedateien
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 99445275a8f92622f451e8a88082dc2b28fb60b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414060"
---
# <a name="binary-output-files"></a>Binäre Ausgabedateien

Streams wurden ursprünglich für Text entwickelt, deswegen ist die Standardmethode für die Ausgabe „text“. Im Textmodus wird Sie das Zeilenumbruchzeichen (hexadezimal 10) auf einen Zeilenumbruch an (nur 16-Bit) erweitert. Die Erweiterung kann Probleme verursachen, wie hier gezeigt wird:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Sie erwarten möglicherweise, dass dieses Programm die Bytesequenz { 99, 0, 10, 0 } ausgibt; stattdessen wird { 99, 0, 13, 10, 0 } ausgegeben, wodurch Probleme für ein Programm verursacht werden, das eine binäre Eingabe erwartet. Wenn sie eine echte binäre Ausgabe benötigen, in der die Zeichen nicht übersetzt geschrieben sind, können Sie die binäre Ausgabe mithilfe des openmode-Konstruktorarguments [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) angeben:

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)<br/>
