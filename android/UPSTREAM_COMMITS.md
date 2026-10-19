# Lyra .5 upstream commits

Applied to main in this order, including both endpoints:

- `9688d01e5ab46e07ec8d207f9f470331e1fe2c3a` fake_id0: read unterminated result string by length
- `4a1dbac41fc25db96b7a6211e474b08bf93312ee` fake_id0: replay fstat for descriptors that aren't paths
- `7f2fab0fb3a9e15f63ac47497ebc29d72281206e` link2symlink: count faked hard links in the emulated fstat
- `0439248ae494c1b10c796e34d90ec497499c1aac` sysvipc: back shared memory with memfd where /dev/ashmem is closed
- `04c28b7dd1efed8de1df02a887f25d0d0ed8192c` fake_id0: keep the group when chown(2) passes -1 for it
- `77310de75b126b2667b652dfee7cde08f9ec4af2` fake_id0: apply chmod through /proc/self/fd to the open file's record
- `54733e84c38d12a0a163c68926e2392fa08cbb1a` fake_id0: apply chmod modes to the real file as well
- `ea0e9b6d41d340eebf896742604f6b40cf22ff0b` fake_id0: record only the permission bits of a chmod mode
- `fdbed740dfe4fbfe3669b3db2e62e42bfd72a9b1` fake_id0: record fchmodat2(fd, "", mode, AT_EMPTY_PATH)
- `788c48205be6199b5f2076ae5304277588f978b9` fake_id0: write the chmod record once the kernel has applied the mode
- `38a60cbed019a8f12e698f5fb8d869e83564ad2b` fake_id0: follow mode changes made through POSIX ACLs
- `1a41a193e809b53942a0c708540ab2962632d28f` fake_id0: compare statx's group with the real gid, not the uid
- `cf393e0ea3ee56421ff0becf5ef7901519a2a8f2` fake_id0: apply ownership records to statx
- `ccd4b745b474cb67dc0bcec8eeddd5667391dac9` fake_id0: apply ownership records to fstatat(fd, "", AT_EMPTY_PATH)
- `32d70f75743de0f76c19db123f4ee549fc4af5cb` fake_id0: keep the id mapping of fstatat(AT_EMPTY_PATH) on non-files
- `66b112ed38c6433d63f9e55e2d5fd5241fd75d5e` fake_id0: move ownership records on renameat2
- `53b2159cda491892168bc591084d7082f2ff270c` fake_id0: name the record of "dir/" after "dir"
- `e8a6c0ebe02a7acde4a3fa60399f1fc158d892f0` fake_id0: remove orphaned records along with their directory
- `4a27ca61ff7a800cdcac3bc616929bba7a484c74` fake_id0: move records once the kernel has renamed the file
- `9bd53079d25737ac739e1210cd490c49377d0cbe` seccomp: run fork(2) as clone(2) when the outer policy rejects it
- `e2d843ee6dab076ea0ed1ffd5d0ea12232185499` seccomp: give the child of fork(2) run as clone(2) its registers back
