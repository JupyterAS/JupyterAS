# jupyter For Atmospheric Scientists

## Description
Docker images of Jupyterlab with Python3, C, Fortan, Grads, Julia, R and Metpy, Siphon, atmos, basemap, ncl_to_Python, Cartopy, ecmwf-api.

## Software Shortcut

| ![https://img.bugatii100peagle.cn/2020/02/18/44d5d10d73152.png](https://img.bugatii100peagle.cn/2020/02/18/44d5d10d73152.png) | ![https://img.bugatii100peagle.cn/2020/02/18/362d47fcfb311.png](https://img.bugatii100peagle.cn/2020/02/18/362d47fcfb311.png)  |
| ------------ | ------------- |
| ![https://img.bugatii100peagle.cn/2020/02/18/36c7dd118359b.png](https://img.bugatii100peagle.cn/2020/02/18/36c7dd118359b.png) | ![https://img.bugatii100peagle.cn/2020/02/18/ec9bbcf04edf9.png](https://img.bugatii100peagle.cn/2020/02/18/ec9bbcf04edf9.png)|

No difficult setting and install, just using it.(Especially Basemap, the nightmare as meteorological major)

## Step for Using

The minimum hardware of Server is 1vCPU & 2GB. Ensure network is fine and access 8000 port, which can change to other number by `run` cmd.

Recommend using [BT Panel](https://www.bt.cn/)

### Configure Docker

Install Docker latest.

```
# remove old version docker
sudo apt-get remove docker docker-engine docker.io

# install dependency
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

# insatll Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs)  stable"
sudo apt-get update
sudo apt-get install docker-ce
```

You con run `docker -v` to test install finished.

### Available IMG

There are some packed img listing below 

| Name                                                         | Size     | Python3 C Grads Julia R | Metpy Siphon atmos | basemap | ncl_to_Python | Cartopy | ecmwf-api | netcdf | Fortan |
| ------------------------------------------------------------ | -------- | ----------------------- | ------------------ | ------- | ------------- | ------- | --------- | ------ | ------ |
| jupytercgmsabefcn:v1                                         | 3.001 GB | √                       | √                  | √       |               | √       | √         | √      | √      |
| [jupytercgrads_metpy_siphon_atmos_nal_ecmwf_fortran:v1](https://gitee.com/bugatti100Peagle/jupyter-For-Atmospheric-Scientists/blob/master/jupytercgrads_metpy_siphon_atmos_ncl_ecmwf_fortran.md) | 2.600 GB | √                       | √                  |         | √             |         | √         |        | √      |
| jupytercgrads:1                                              | 1.871 GB | √                       |                    |         |               |         |           |        |        |
| jupytercgrads_metpy_siphon_atmos:v1                          | 1.978 GB | √                       | √                  |         |               |         |           |        |        |
| jupytercgrads_metpy_siphon_atmos_basemap:v1                  | 2.794 GB | √                       | √                  | √       |               |         |           |        |        |
| jupytercgrads_metpy_siphon_atmos_basemap_ecmwf_fortran:v1    | 2.794 GB | √                       | √                  | √       |               |         | √         |        | √      |
| [jupytercgrads_metpy_siphon_atmos_basemap_ecmwf_fortran_cartopy:v1](https://gitee.com/bugatti100Peagle/jupyter-For-Atmospheric-Scientists/blob/master/jupytercgrads_metpy_siphon_atmos_basemap_ecmwf_fortran_cartopy.md) | 2.959 GB | √                       | √                  | √       |               | √       | √         |        | √      |

For example, in order to use `jupytercgmsabefcn:v1` , you need pull img by cmd

```
docker pull registry.cn-shanghai.aliyuncs.com/bugatii100peagle/jupytercgmsabefcn:v1
```

### Run Docker

```
mkdir -p ~/jupyterlab/workspace
docker run --name jupytercgmsabefcn -d -p 8000:8888 -v `pwd`/jupyterlab:/workspace -w /workspace -e GRANT_SUDO=yes --user root registry.cn-shanghai.aliyuncs.com/bugatii100peagle/jupytercgmsabefcn jupyter-lab --no-browser --port=8888 --ip=0.0.0.0 --allow-root
```

### Using form Client Device

Open `http://<Server_IP>:8000`. Default is no passwd, just type enter.

![https://img.bugatii100peagle.cn/2020/02/20/442292d9a302a.png](img/README.en/442292d9a302a.png)

## TODO

- [x] 1. Multi-language for doc
- [ ] 2. Integrate more comm tools
- [ ] 3. Try solve the confilect of NCL and Basemap
- [ ] 4. Fix low version Grads can not open `.nc` files

## Join Us

It is our honor for you to use. If fell convenient please reward us a star.

For any problems or suggestions raise an issue.

For pure env of Jupyter to insatll, related blog :[气象人的Jupyterlab](https://blog.bugatii100peagle.cn/2020/02/17/%E6%B0%94%E8%B1%A1%E4%BA%BA%E7%9A%84JupyterLab/).

## Donation
|![https://bugatii100peaglepics.oss-cn-qingdao.aliyuncs.com/HexoTheme/img/WX_cr.png](https://bugatii100peaglepics.oss-cn-qingdao.aliyuncs.com/HexoTheme/img/WX_cr.png)| ![https://bugatii100peaglepics.oss-cn-qingdao.aliyuncs.com/HexoTheme/img/ZFB_cr.jpg](https://bugatii100peaglepics.oss-cn-qingdao.aliyuncs.com/HexoTheme/img/ZFB_cr.jpg) |
| ------------ | ------------- |