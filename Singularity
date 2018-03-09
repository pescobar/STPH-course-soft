BootStrap: docker
From: ubuntu:16.04

%post
    # install some system deps
    apt-get -y update
    apt-get -y install locales curl bzip2 less more
    locale-gen en_US.UTF-8
    apt-get clean

    # download and install miniconda2
    curl -sSL -O https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh -p /opt/miniconda3 -b
    rm -fr Miniconda3-latest-Linux-x86_64.sh
    export PATH=/opt/miniconda3/bin:$PATH
    conda update -n base conda
    conda config --add channels conda-forge
    conda config --add channels bioconda

    # use conda to install some bioinfo tools
    conda install --yes -c bioconda samtools==1.7
    conda install --yes -c bioconda bwa==0.7.17
    conda install --yes -c bioconda trimmomatic==0.36
    conda install --yes -c bioconda perl-findbin==1.51
    conda install --yes -c bioconda fastqc==0.11.7
    conda install --yes -c bioconda seqprep==1.2
    conda install --yes -c bioconda gatk4==4.0.1.1
    conda install --yes -c bioconda igv=2.3.98
    conda install --yes -c bioconda vcftools==0.1.15
    conda install --yes -c bioconda snpeff=4.3.1t-0
    conda install --yes -c bioconda varscan==2.4.3
    conda install --yes -c bioconda muscle==3.8.1551
    conda install --yes -c bioconda mafft==7.313
    conda install --yes -c bioconda raxml==8.2.10
    conda install --yes -c bioconda beast==1.8.4
    conda install --yes -c bioconda phylip==3.696
    conda install --yes -c bioconda paml==4.9
    conda install --yes -c conda-forge r-base==3.4.1

%environment
    export LANG=en_US.UTF-8
    export LANGUAGE=en_US:en
    export LC_ALL=en_US.UTF-8
    export PATH=/opt/miniconda3/bin:$PATH

%apprun samtools
    samtools

%apprun bwa
    bwa

%apprun trimmomatic
    trimmomatic

%apprun fastqc
    fastqc

%apprun seqprep
    seqprep

%apprun gatk4
    gatk-launch

%apprun vcftools
    vcftools

%apprun snpeff
    snpeff

%apprun varscan
    varscan

%apprun muscle
    varscan

%apprun mafft
    mafft

%apprun raxml
    raxmlHPC-PTHREADS

%apprun beast
    beast

%apprun phylip
    phylip

%apprun paml
    codeml

%apprun R
    R
