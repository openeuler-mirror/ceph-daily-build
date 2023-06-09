# ceph-daily-build
Daily Ceph build and test on openEuler

------------------------------------------------------------

|  Key   | Value  |
|  ----  | ----  |
| Ceph version  | master |
| openEuler version | 22.03 LTS SP1 |
| Arch  | arm64 |
| Patch  | [openEuler_RPM_support](./0001-Add-openEuler-support-for-rpm-spec.patch) |
| Extra needed packages | https://eur.openeuler.openatom.cn/coprs/wxy2933/ceph_dev/ |
| Action | **Build from source**, **Unit test**, **Build RPM package**|
| Result | https://github.com/openeuler-mirror/ceph-daily-build/actions/workflows/build-and-test.yaml |
| Period | UTC 1300 daily |
| Recheck By Hand | comment 'recheck' in any issue |

## Known Issue

The unit test `unittest_mempool` raises error:
```
[ RUN      ] mempool.check_shard_select
/opt/code/ceph/src/test/test_mempool.cc:433: Failure
Expected: (missed) < (mempool::num_shards / 2), actual: 28 vs 16
[  FAILED  ] mempool.check_shard_select (107 ms)
```

This is an error that Ceph Upstream alwasy raise as well. It needs be fixed upstream.
