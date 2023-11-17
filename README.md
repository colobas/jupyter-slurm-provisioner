# Jupyter slurm provisioner

Fork of [jupyter-slurm-provisioner](https://FZJ-JSC/jupyter-slurm-provisioner)
without the dependency on `jutil`.

## Installation
`pip install git+https://github.com/colobas/jupyter-slurm-provisioner.git`


## Example `kernel.json`

``` json
{
    "display_name": "Slurm Kernel",
    "language": "python",
    "metadata": {
        "debugger": true,
        "kernel_provisioner": {
            "config": {
                "gpus": "0",
                "partition": "this,that,other",
                "account": "...",
                "reservation": null,
                "runtime": 30,
                "jobid": null,
                "kernel_argv": [
                    "~/.local/share/jupyter/kernels/my_kernel/kernel.sh",
                    "-f",
                    "{connection_file}"
                ],
                "env": {
                    "PATH": "/some/additional/path:$PATH",
                    "SOME_VAR": "some_value"
                }
            },
            "provisioner_name": "slurm-provisioner"
        }
    }
}
```
