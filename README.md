### Install with GPU support

Clone the project
```
git clone https://github.com/jlizier/jidt.git
```
Install CUDA 9.2 at `https://developer.nvidia.com/cuda-92-download-archive` (**CUDA 11.6 does not work**).
Install JAVA (already have) and:
```
sudo apt-get install openjdk-8-jre openjdk-8-jdk
```
Install Apache Ant
```
cd /home/yiren
wget https://dlcdn.apache.org//ant/binaries/apache-ant-1.10.14-bin.zip
unzip apache-ant-1.10.14-bin.zip
```
Put the following in `/home/yiren/.bashrc`
```
export PATH=/usr/local/cuda-9.2/bin${PATH:+:${PATH}}
export ANT_HOME=/home/yiren/apache-ant-1.10.14
export PATH=$PATH:$ANT_HOME/bin
```

Following the guide `https://github.com/jlizier/jidt/wiki/GPU`. `cd /home/yiren/jidt` and run `ant gpu` and `ant jar`.
```bash
(py38) yiren@dartmouth-CS110A:~/jidt$ ant gpu
Buildfile: /home/yiren/jidt/build.xml

init:
    [mkdir] Created dir: /home/yiren/jidt/bin
    [mkdir] Created dir: /home/yiren/jidt/bin/cuda
    [mkdir] Created dir: /home/yiren/jidt/unittests/bin
    [mkdir] Created dir: /home/yiren/jidt/unittests/bin/cuda
    [mkdir] Created dir: /home/yiren/jidt/unittests/reports

gpu:
     [exec] Compiling diagnostics script
     [exec] CUDA compute capability found: -gencode arch=compute_61,code=sm_61 -gencode arch=compute_61,code=sm_61
     [exec] nvcc -O3 -D_FORCE_INLINES -Xcompiler -Wall -gencode arch=compute_61,code=sm_61 -gencode arch=compute_61,code=sm_61  -g -G -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -x cu -Xcompiler -fPIC -c gpuKnnLibrary.c -o ../bin/cuda/gpuKnnLibrary.o
     [exec] ./cub/cub/block/specializations/../../block/../util_ptx.cuh(702): warning: function "__all"
     [exec] /usr/local/cuda-9.2/bin/../targets/x86_64-linux/include/device_atomic_functions.h(181): here was declared deprecated ("__all() is deprecated in favor of __all_sync() and may be removed in a future release (Use -Wno-deprecated-declarations to suppress this warning).")
     [exec]
     [exec] ./cub/cub/block/specializations/../../block/../util_ptx.cuh(728): warning: function "__any"
     [exec] /usr/local/cuda-9.2/bin/../targets/x86_64-linux/include/device_atomic_functions.h(180): here was declared deprecated ("__any() is deprecated in favor of __any_sync() and may be removed in a future release (Use -Wno-deprecated-declarations to suppress this warning).")
     [exec]
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 3860; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 3948; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 4036; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 4124; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 4212; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 5298; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 5386; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 5474; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 5562; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 5650; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 9340; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 9428; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 9516; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 9604; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 9692; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 11166; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 11254; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 11342; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 11430; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 11518; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 12604; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 12692; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 12780; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 12868; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 12956; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 16680; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 16768; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 16856; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 16944; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ptxas /tmp/tmpxft_00007dbd_00000000-5_gpuKnnLibrary.ptx, line 17032; warning : Instruction 'shfl' without '.sync' is deprecated since PTX ISA version 6.0 and will be discontinued in a future PTX ISA version
     [exec] ar -r ../bin/cuda/libgpuKnnLibrary.a ../bin/cuda/gpuKnnLibrary.o
     [exec] g++ -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -O3 -Wall -Wextra -Wno-unused-parameter -g -x c -std=c99 -fPIC -c digamma.c -o ../bin/cuda/digamma.o
     [exec] g++ -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -O3 -Wall -Wextra -Wno-unused-parameter -g -x c -std=c99 -fPIC -c gpuMILibrary.c -o ../bin/cuda/gpuMILibrary.o
     [exec] g++ -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -O3 -Wall -Wextra -Wno-unused-parameter -g -x c -std=c99 -fPIC -c gpuCMILibrary.c -o ../bin/cuda/gpuCMILibrary.o
     [exec] ar: creating ../bin/cuda/libgpuKnnLibrary.a
     [exec] g++ -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -O3 -Wall -Wextra -Wno-unused-parameter -g -x c -std=c99 -fPIC -c kraskovCuda.c -o ../bin/cuda/kraskovCuda.o
     [exec] nvcc -O3 -D_FORCE_INLINES -Xcompiler -Wall -gencode arch=compute_61,code=sm_61 -gencode arch=compute_61,code=sm_61  -g -G -I. -I./cub -I/usr/lib/jvm/java-8-openjdk-amd64/include -I/usr/lib/jvm/java-8-openjdk-amd64/include/linux -Xcompiler -fPIC -shared -o ../bin/cuda/libKraskov.so ../bin/cuda/digamma.o ../bin/cuda/gpuMILibrary.o ../bin/cuda/gpuCMILibrary.o ../bin/cuda/kraskovCuda.o -L. -L../bin/cuda -lcuda -lcudart -lgpuKnnLibrary

BUILD SUCCESSFUL
Total time: 3 seconds
(py38) yiren@dartmouth-CS110A:~/jidt$ ant jar
Buildfile: /home/yiren/jidt/build.xml

init:

compile:
    [javac] Compiling 249 source files to /home/yiren/jidt/bin
    [javac] warning: [options] bootstrap class path not set in conjunction with -source 7
    [javac] Note: Some input files use or override a deprecated API.
    [javac] Note: Recompile with -Xlint:deprecation for details.
    [javac] Note: Some input files use unchecked or unsafe operations.
    [javac] Note: Recompile with -Xlint:unchecked for details.
    [javac] 1 warning
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/mixed/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/utils/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/kozachenko/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/kernel/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/symbolic/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/discrete/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/spiking/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/networkinference/interregional/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/gaussian/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/spiking/integration/package-info.class
    [javac] Creating empty /home/yiren/jidt/bin/infodynamics/measures/continuous/kraskov/package-info.class

jar:
      [jar] Building jar: /home/yiren/jidt/infodynamics.jar

BUILD SUCCESSFUL
Total time: 2 seconds
(py38) yiren@dartmouth-CS110A:~/jidt$

```

`ant gputest` and `ant junit` (`https://github.com/jlizier/jidt/wiki/AntScripts`) will fail (missing JUnit installation).

>You wish to run the JUnit test cases - this requires JUnit - for how to run JUnit with our ant script see JUnitTestCases and AntScripts;

But this is fine, based on author's response (https://github.com/jlizier/jidt/issues/75#issuecomment-471368088)


### Notes
Same error met at `https://github.com/jlizier/jidt/issues/80` and is solved by
```
sudo apt-get install openjdk-8-jre openjdk-8-jdk
```

`ant gputest` and `ant junit` (`https://github.com/jlizier/jidt/wiki/AntScripts`) will fail (missing JUnit installation).

>You wish to run the JUnit test cases - this requires JUnit - for how to run JUnit with our ant script see JUnitTestCases and AntScripts;

But this is fine, based on author's response (https://github.com/jlizier/jidt/issues/75#issuecomment-471368088)
