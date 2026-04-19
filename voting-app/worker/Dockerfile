FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /source
COPY Worker.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:7.0
WORKDIR /app
RUN addgroup --system appgroup && adduser --system --ingroup appgroup appuser
COPY --from=build /app .
RUN chown -R appuser:appgroup /app
USER appuser
ENTRYPOINT ["dotnet", "Worker.dll"]