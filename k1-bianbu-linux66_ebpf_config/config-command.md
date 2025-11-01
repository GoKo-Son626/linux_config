 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:36:45 
> git status
位于分支 k1-bl-v2.2.y
您的分支与上游分支 'origin/k1-bl-v2.2.y' 一致。

未跟踪的文件:
  （使用 "git add <文件>..." 以包含要提交的内容）
	tools/bpf/FEATURE-DUMP1
	tools/bpf/bpftool/FEATURE-DUMP1
	tools/lib/bpf/include
	tools/lib/zlib/

提交为空，但是存在尚未跟踪的文件（使用 "git add" 建立跟踪）
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:36:47 
> git diff  
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:36:53 
> history | grep tools
  449  2025-04-10 17:12  apt install -y vim\napt install -y wget\n\napt install -y sqlite3 (used by a test, not needed for the build to complete)\n\napt install -y curl\napt install -y git\napt install -y build-essential\napt install -y pkg-config\n\napt install -y libgit2-1.1 / apt install -y libgit2-28 (older Ubuntu)\napt install -y libgit2-dev\n\napt install -y xapian-tools\n\napt install -y libinline-c-perl\napt install -y libany-uri-escape-perl\napt install -y libdbd-sqlite3-perl\napt install -y libsearch-xapian-perl\napt install -y libmail-imapclient-perl\napt install -y libplack-middleware-reverseproxy-perl\napt install -y libcrypt-cbc-perl\napt install -y liblinux-inotify2-perl\n\nwget https://public-inbox.org/public-inbox.git/snapshot/public-inbox-1.7.0.tar.gz\ntar zxvf public-inbox-1.7.0.tar.gz\ncd public-inbox-1.7.0\n\nmake clean\nperl Makefile.PL INSTALLDIRS=vendor\nmake OPTIMIZE="-O2 -g -Wall" LD_RUN_PATH="" -j2 V=1 VERBOSE=1\nmake pure_install DESTDIR=/tmp/public-index\n\nmkdir -p /tmp/test\nPERL_INLINE_DIRECTORY=/tmp/test make test\n\nexport PERL5LIB=${PERL5LIB}:/tmp/public-index/usr/share/perl5\n/tmp/public-index/usr/bin/lei
  457  2025-04-10 17:24  apt install -y vim\napt install -y wget\n\napt install -y curl\napt install -y git\napt install -y build-essential\napt install -y pkg-config\n\napt install -y libgit2-dev\n\napt install -y xapian-tools\n\napt install -y libinline-c-perl\napt install -y libany-uri-escape-perl\napt install -y libdbd-sqlite3-perl\napt install -y libsearch-xapian-perl\napt install -y libmail-imapclient-perl\napt install -y libplack-middleware-reverseproxy-perl\napt install -y libcrypt-cbc-perl\napt install -y liblinux-inotify2-perl
  695  2025-04-14 15:14  sudo apt update\nsudo apt install -y build-essential libssl-dev flex bison libncurses-dev \\n  libelf-dev dwarves bc u-boot-tools python3\n
  712  2025-04-14 16:03  sudo apt install net-tools
  851  2025-04-16 01:28  ./titantools_for_linux-1.0.35-beta.
  856  2025-04-16 03:23  ./titantools_for_linux-1.0.35-beta.AppImage &
  891  2025-04-16 15:47  sudo apt install u-boot-tools\n
  898  2025-04-16 16:26  # 安装依赖库\nsudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev\n\n# 下载并编译工具链（以 Linux 版本为例）\ngit clone https://github.com/riscv-collab/riscv-gnu-toolchain\ncd riscv-gnu-toolchain\n./configure --prefix=/opt/riscv --enable-multilib\nmake linux
 1411  2025-04-18 12:15  ls /etc/initramfs-tools/initramfs.conf
 1412  2025-04-18 12:15  vim /etc/initramfs-tools/initramfs.conf
 1645  2025-04-26 23:24  GDK_SCALE=1 GDK_DPI_SCALE=1 /opt/deepinwine/tools/spark_run_v4.sh Spark-weixin 3.9.10deepin1 c:/Program\ Files/Tencent/WeChat/WeChat.exe -f --no-sandbox\n
 1915  2025-05-04 09:57  rustup target add riscv64gc-unknown-none-elf\ncargo install cargo-binutils\nrustup component add llvm-tools-preview\nrustup component add rust-src
 1916  2025-05-04 09:57  rustup target add riscv64gc-unknown-none-el\ncargo install cargo-binutils\nrustup component add llvm-tools-preview\nrustup component add rust-src
 1952  2025-05-04 20:06  sudo apt update\nsudo apt install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk \\n    build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev \\n    python3 python3-pip\n
 1967  2025-05-04 20:37  sudo apt update\nsudo apt install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev\n
 2202  2025-05-15 11:39  sudo apt-get install libinput-tools
 2204  2025-05-15 11:40  sudo apt install aptitude\nsudo aptitude install libinput-tools\n
 2206  2025-05-15 11:43  sudo apt install libinput10=1.20.0-1ubuntu0.1 libinput-tools\n
 2543  2025-05-23 15:09  pip install --upgrade pip setuptools\npip install openai-whisper --no-deps\n
 2813  2025-05-30 15:29  sudo apt install libinput-tools ruby xdotool
 2827  2025-05-30 19:26  llls❯ sudo apt-get install sunxi-tools\n
 2828  2025-05-30 19:26  sudo apt-get install sunxi-tools\n
 4251  2025-08-04 15:03  chmod +x titantools_for_linux-1.0.35-beta.AppImage
 4252  2025-08-04 15:03  ./titantools_for_linux-1.0.35-beta.AppImage
 4259  2025-08-04 15:54  mv titantools_for_linux-1.0.35-beta.zip bianbu-24.04-minimal-k1-v2.1-release-20250124140410.zip bianbu-25.04-minimal-k1-v3.0-release-20250725114639.zip bianbu
 4338  2025-08-04 23:16  mv 初步认识编译库及编译工具.md Compilation-libraries-and-tools.md
 4343  2025-08-04 23:24  nvim Compilation-libraries-and-tools.md
 4393  2025-08-05 00:07  # 指定 eBPF 头文件在你编译好的内核源码树里的位置\nexport BPF_INCLUDE="/home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf"
 4396  2025-08-05 00:08  ls /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf/
 4405  2025-08-05 00:09  make \\nCC="/home/goko/opt/riscv-linux/bin/riscv64-unknown-linux-gnu-gcc" \\nARCH=riscv \\nBPF_INCLUDE="/home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf"
 4413  2025-08-05 00:21  make clean\nmake \\nCC="/home/goko/opt/riscv-linux/bin/riscv64-unknown-linux-gnu-gcc" \\nARCH=riscv \\nBPF_INCLUDE="/home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf"
 4420  2025-08-05 00:28  # 检查内核源码根目录的权限\nls -ld /home/goko/文档/sp-k1-bianbu/linux-6.6/\n\n# 检查 bpf 头文件目录的权限\nls -ld /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf/\n\n# 检查 bpf_helpers.h 文件本身的权限\nls -l /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf/bpf_helpers.h
 4426  2025-08-05 00:35  ls /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf/
 4427  2025-08-05 00:35  cp /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf ./
 4429  2025-08-05 00:35  cp /home/goko/文档/sp-k1-bianbu/linux-6.6/tools/lib/bpf ./ -r
 4552  2025-08-05 10:56  sudo apt update\nsudo apt install -y git autoconf automake autotools-dev curl python3 python3-pip \\nlibmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo \\ngperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build pkg-config \\nlibssl-dev libisl-dev libelf-dev
 4651  2025-08-05 17:25  sl tools
 4652  2025-08-05 17:25  ls tools
 4718  2025-08-05 18:07  ls tools
 4719  2025-08-05 18:07  cd tools/bpf/bpftool/
 4746  2025-08-05 18:23  rm -rf ~/repo/linux-6.6/tools/lib/bpf/include\nln -s ~/ebpf_riscv_project/libbpf/include ~/repo/linux-6.6/tools/lib/bpf/include\n
 4748  2025-08-05 18:23  # 软链 zlib 目录到内核源码工具链路径\nmkdir -p ~/repo/linux-6.6/tools/lib/zlib\nln -s ~/ebpf_riscv_project/zlib ~/repo/linux-6.6/tools/lib/zlib/include\n\n# 清理旧编译文件\nmake clean\n\n# 编译，确保带上 EXTRA_CFLAGS 和 EXTRA_LDFLAGS\nmake CC=riscv64-unknown-linux-gnu-gcc ARCH=riscv CROSS_COMPILE=riscv64-unknown-linux-gnu- VMLINUX_BTF=/home/goko/riscv_dev/linux-6.6/vmlinux FEATURE_USER=1 \\nEXTRA_CFLAGS="-I$(pwd)/tools/lib/zlib/include" \\nEXTRA_LDFLAGS="-L$(pwd)/tools/lib/zlib/lib -lz"\n
 4755  2025-08-05 18:37  make CC=riscv64-unknown-linux-gnu-gcc \\n     ARCH=riscv \\n     CROSS_COMPILE=riscv64-unknown-linux-gnu- \\n     VMLINUX_BTF=/full/path/to/vmlinux \\n     FEATURE_USER=1 \\n     EXTRA_CFLAGS="-I/home/goko/ebpf_riscv_project/zlib -I/home/goko/ebpf_riscv_project/libbpf/include -I/home/goko/ebpf_riscv_project/deps/include" \\n     EXTRA_LDFLAGS="-L/home/goko/ebpf_riscv_project/zlib -lz -L/home/goko/ebpf_riscv_project/deps/lib -lelf" \\n     -C tools/bpf\n
 4756  2025-08-05 18:37  cd tools/bpf/bpftool/
 5154  2025-08-14 01:56  ls bpftrace/tools/
 5409  2025-08-18 00:41  mv ./Compilation-libraries-and-tools.md ./ebpf-and-use-libbpf.md ./hexo-blog.md ./libbpf-bcc-and-bpftrace.md ./linux-kernel-drivers.md ./Platform-bus.md ./qspinlock.md ./riscv-toolchains.md ./the-Three-Basic-Linux-Driver-Models.md ./use-bpftrace-on-k1.md ../../../my-blog_bak/avoid
 6432  2025-08-31 16:45  ls tools
 6650  2025-09-04 23:49  rm Compilation-libraries-and-tools.md ebpf-and-use-libbpf.md hexo-blog.md kernel-1.md kernel.md libbpf-bcc-and-bpftrace.md linux-kernel-drivers.md Platform-bus.md qspinlock.md riscv-toolchains.md the-Three-Basic-Linux-Driver-Models.md u-boot.md use-bpftrace-on-k1.md
 8585  2025-09-26 13:28  # 激活你的虚拟环境\nsource venv39/bin/activate\n\n# 升级 pip/setuptools/wheel，避免奇怪的依赖问题\npip install --upgrade pip setuptools wheel\n\n# 先手动装缺失的依赖\npip install requests[socks] pycryptodome pybase64\n
 8587  2025-09-26 13:30  pip install --upgrade pip setuptools wheel\n
 8590  2025-09-26 13:31  python -m pip install --upgrade pip setuptools wheel\n
10257  2025-10-29 23:01  cp ../new-ubuntu/readme.md linux-tools-config.md
10258  2025-10-29 23:01  cat linux-tools-config.md
10260  2025-10-29 23:02  git add linux-tools-config.md
10261  2025-10-29 23:03  cat repo/linux-configer/linux-tools-config.md
10262  2025-10-29 23:03  nvim repo/linux-configer/linux-tools-config.md
10265  2025-10-29 23:19  nvim linux-tools-config.md
10268  2025-10-29 23:20  git add linux-tools-config.md
10271  2025-10-29 23:20  git commit -m "linux-tools-config.md : su, proxy, sudoers, source, wifi, ifconfig, basic, ssh, Time, Touchpad scroll, zsh, ssh-key, neovim, nextcloud, tailscale, shallow clone, LFS, tftp, riscv-toolchain, update_git-repo, fusuma, VMWARE"\n
10279  2025-10-29 23:21  nvim linux-tools-config.md
10341  2025-10-30 15:55  nvim linux-tools-config.md
10534  2025-10-30 17:22  apt install -y vim\napt install -y wget\n\napt install -y curl\napt install -y git\napt install -y build-essential\napt install -y pkg-config\n\napt install -y libgit2-dev\n\napt install -y xapian-tools\n\napt install -y libinline-c-perl\napt install -y libany-uri-escape-perl\napt install -y libdbd-sqlite3-perl\napt install -y libsearch-xapian-perl\napt install -y libmail-imapclient-perl\napt install -y libplack-middleware-reverseproxy-perl\napt install -y libcrypt-cbc-perl\napt install -y liblinux-inotify2-perl
10939  2025-10-31 11:35  ls tools
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:37:46 
> ls tools/bpf/bpftool/
bash-completion  btf_dumper.o  cgroup.c  disasm.d       feature.o  iter.o         libbpf  main.h    map_perf_ring.c   netlink_dumper.d  perf.o           profiler.bpf.o   struct_ops.c  vmlinux.h
bootstrap        btf.o         cgroup.d  disasm.o       gen.c      jit_disasm.c   link.c  main.o    map_perf_ring.d   netlink_dumper.h  pid_iter.bpf.o   profiler.skel.h  struct_ops.d  xlated_dumper.c
btf.c            cfg.c         cgroup.o  Documentation  gen.d      json_writer.c  link.d  Makefile  map_perf_ring.o   netlink_dumper.o  pid_iter.skel.h  prog.c           struct_ops.o  xlated_dumper.d
btf.d            cfg.d         common.c  feature.c      gen.o      json_writer.d  link.o  map.c     net.c             net.o             pids.c           prog.d           tracelog.c    xlated_dumper.h
btf_dumper.c     cfg.h         common.d  feature.d      iter.c     json_writer.h  main.c  map.d     net.d             perf.c            pids.d           prog.o           tracelog.d    xlated_dumper.o
btf_dumper.d     cfg.o         common.o  FEATURE-DUMP1  iter.d     json_writer.o  main.d  map.o     netlink_dumper.c  perf.d            pids.o           skeleton         tracelog.o
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:38:13 
> ls                   
arch   built-in.a  COPYING  crypto         drivers  include  io_uring  Kbuild   kernel  LICENSES     Makefile  modules.builtin          modules.order   net     rt-linux  samples  security  System.map  usr   vmlinux    vmlinux.o
block  certs       CREDITS  Documentation  fs       init     ipc       Kconfig  lib     MAINTAINERS  mm        modules.builtin.modinfo  Module.symvers  README  rust      scripts  sound     tools       virt  vmlinux.a
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:41:04 
> git remote -v
origin	https://gitee.com/bianbu-linux/linux-6.6.git (fetch)
origin	https://gitee.com/bianbu-linux/linux-6.6.git (push)
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:41:09 
> git status   
位于分支 k1-bl-v2.2.y
您的分支与上游分支 'origin/k1-bl-v2.2.y' 一致。

未跟踪的文件:
  （使用 "git add <文件>..." 以包含要提交的内容）
	tools/bpf/FEATURE-DUMP1
	tools/bpf/bpftool/FEATURE-DUMP1
	tools/lib/bpf/include
	tools/lib/zlib/

提交为空，但是存在尚未跟踪的文件（使用 "git add" 建立跟踪）
 ~/repo/linux-6.6  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:17 
> cd tools             
 ~/repo/linux-6.6/tools  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:23 
> ls
accounting  bootconfig  build  cgroup   crypto     edid      firmware  hv   include  laptop  lib       memory-model  net      pci     perf   rcu      spi      thermal  tracing  verification  wmi
arch        bpf         certs  counter  debugging  firewire  gpio      iio  kvm      leds    Makefile  mm            objtool  pcmcia  power  scripts  testing  time     usb      virtio        workqueue
 ~/repo/linux-6.6/tools  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:24 
> cd lib      
 ~/repo/linux-6.6/tools/lib  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:29 
> ls
api  argv_split.c  bitmap.c  bpf  ctype.c  find_bit.c  hweight.c  list_sort.c  perf  rbtree.c  slab.c  str_error_r.c  string.c  subcmd  symbol  thermal  vsprintf.c  zalloc.c  zlib
 ~/repo/linux-6.6/tools/lib  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:29 
> cd zlib     
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?3 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:35 
> ls
include
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:36 
> ls include           
include
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:38 
> ls include -al
lrwxrwxrwx 1 goko goko 34  8月  5 18:23 include -> /home/goko/ebpf_riscv_project/zlib
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:43:46 
> ls ../bpf/include -al
lrwxrwxrwx 1 goko goko 44  8月  5 18:23 ../bpf/include -> /home/goko/ebpf_riscv_project/libbpf/include
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:44:55 
> ls ../bpf/include    
../bpf/include
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:01 
> ls ../bpf/       
bpf.c            bpf_gen_internal.h  bpf_prog_linfo.c  btf_dump.c  elf.c         hashmap.h  libbpf_common.h  libbpf_internal.h  libbpf.pc.template  linker.c   nlattr.c     relo_core.h      str_error.c  strset.h    zip.c
bpf_core_read.h  bpf.h               bpf_tracing.h     btf.h       gen_loader.c  include    libbpf_errno.c   libbpf_legacy.h    libbpf_probes.c     Makefile   nlattr.h     ringbuf.c        str_error.h  usdt.bpf.h  zip.h
bpf_endian.h     bpf_helpers.h       btf.c             Build       hashmap.c     libbpf.c   libbpf.h         libbpf.map         libbpf_version.h    netlink.c  relo_core.c  skel_internal.h  strset.c     usdt.c
 ~/repo/linux-6.6/tools/lib/zlib  k1-bl-v2.2.y ?4 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:05 
> cd ...    
 ~/repo/linux-6.6/tools  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:13 
> ls        
accounting  bootconfig  build  cgroup   crypto     edid      firmware  hv   include  laptop  lib       memory-model  net      pci     perf   rcu      spi      thermal  tracing  verification  wmi
arch        bpf         certs  counter  debugging  firewire  gpio      iio  kvm      leds    Makefile  mm            objtool  pcmcia  power  scripts  testing  time     usb      virtio        workqueue
 ~/repo/linux-6.6/tools  k1-bl-v2.2.y ?4 ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:14 
> cd bpf           
 ~/repo/linux-6.6/tools/bpf  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:19 
> ls
bpf_asm.c  bpf_dbg.c  bpf_exp.l  bpf_exp.y  bpf_jit_disasm.c  bpftool  FEATURE-DUMP1  Makefile  resolve_btfids  runqslower
 ~/repo/linux-6.6/tools/bpf  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:45:20 
> ls FEATURE-DUMP1 -al
-rw-rw-r-- 1 goko goko 85  8月  5 18:37 FEATURE-DUMP1
 ~/repo/linux-6.6/tools/bpf  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:46:05 
> cat FEATURE-DUMP1       
feature-libbfd=0
feature-disassembler-four-args=0
feature-disassembler-init-styled=0
 ~/repo/linux-6.6/tools/bpf  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:46:09 
> cat bpftool/FEATURE-DUMP1 
feature-clang-bpf-co-re=1
feature-llvm=0
feature-libcap=0
feature-libbfd=0
feature-libbfd-liberty=0
feature-libbfd-liberty-z=0
feature-disassembler-four-args=0
feature-disassembler-init-styled=0
 ~/repo/linux-6.6/tools/bpf  k1-bl-v2.2.y ?4 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:46:23 
> cd ....                  
 ~/repo -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 11:46:41 
> cd linux-6.6        
