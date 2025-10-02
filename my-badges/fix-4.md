<img src="https://my-badges.github.io/my-badges/fix-4.png" alt="I did 4 sequential fixes." title="I did 4 sequential fixes." width="128">
<strong>I did 4 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/the-ebdm/panhandler/commit/ea19a1da3cad005faf8c9ba042a8f53cbd2ceb2c">ea19a1d</a>: fix: correct module exports to match actual build output

- Change exports from .mjs to .js files (what tsc actually generates)
- Update module field to point to .js instead of .mjs
- This fixes 'Cannot find module @panhandler/core' import errors
- <a href="https://github.com/the-ebdm/panhandler/commit/4e28e037a29885475213ec9c277384f725ba72da">4e28e03</a>: fix: copy node_modules from build stage for proper workspace linking

The build stage has the complete workspace setup with proper linking,
while the deps stage only had package.json files without linking.
- <a href="https://github.com/the-ebdm/panhandler/commit/011111e0c727bfbad34ba665d04a867e89a27f26">011111e</a>: fix: resolve workspace dependencies in Docker build

- Remove --production flag to preserve workspace linking
- Copy workspace configuration (package.json, bunfig.toml) to runtime
- Ensure @panhandler/core and @panhandler/types can be resolved

This fixes the 'Cannot find module @panhandler/core' error in containers.
- <a href="https://github.com/the-ebdm/panhandler/commit/e9349ded8328bc94738cdb434c61f076b2a7ac35">e9349de</a>: fix: resolve GHCR image pull authentication issues

- Update deployment templates to prioritize local imagePullSecrets over global
- Enhance add-github-secret.sh script to support multiple namespaces
- Configure local imagePullSecrets for agents and web services
- Create ghcr-auth secrets in all panhandler environments (dev, staging, prod)

Resolves: 401 Unauthorized errors when pulling from ghcr.io
Status: Image pulls now working successfully ✅


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>