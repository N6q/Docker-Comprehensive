# ==========================================================
# 🌐 FRONTEND (NGINX STATIC WEB)
# ==========================================================
FROM nginx:alpine

# Remove default config that may conflict
RUN rm -rf /etc/nginx/conf.d/default.conf

# Copy your nginx configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Remove default html folder and recreate
RUN rm -rf /usr/share/nginx/html && mkdir -p /usr/share/nginx/html

# Copy all frontend assets
COPY index.html /usr/share/nginx/html/
COPY styles/ /usr/share/nginx/html/styles/
COPY js/ /usr/share/nginx/html/js/

# Verify files copied correctly
RUN ls -la /usr/share/nginx/html/

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
